---
title: 算法练习记录1
---

简单记录下最近做的算法题。

## Signal Tower Deployment Plan

### 题意概述

在$0 \leq x,y \leq 1000$的二维平面内，有两座电波塔为N个用户提供服务，$0\leq N \leq 80000$。电波塔的广播半径可以分别调整，每座电波塔的运营成本与半径的平方成正比。

给出电波塔和每个用户的坐标，求最小总运营成本。

### Spec

Intel(R) Xeon(R) E5-2630 v4 @ 2.20GHz, Time Limit: 1000ms, Memory Limit: 256MB.

### 算法 

Tags: 排序, 枚举, 递推

计算每个用户与两座塔的距离，设存放于结构体数组dist[n]中，结构为`(dist[n].a, dist[n].b)`。根据dist[n].a升序排序dist数组。递推预处理后缀dist[left].b至dist[N-1].b的区间最大值，`left=0..N`

枚举第一座电波塔的广播半径（第一座电波塔覆盖距离最近的n个用户），则第二座电波塔的广播半径等于其余用户最远的距离。枚举求得最小运营成本。

时间复杂度$O(n\log n)$，空间复杂度线性。

### 代码

```cpp
#include<iostream>
#include<cmath>
using namespace std;
#define sqr(x) ((x)*(x))
int x[80005], y[80005], loc[80005];
double r1[80005], r2[80005], r2max[80005];
void quicksort(int begin, int end) {
    if (end - begin < 10) {
        for (int i = begin; i <= end - 1; i++) for (int j = i + 1; j <= end; j++) if (r1[i] > r1[j]) {
            swap(r1[i], r1[j]);
            swap(r2[i], r2[j]);
        }
        return;
    }
    int i = begin, j = end + 1;
    double pivot = r1[begin], r2pivot = r2[begin];
    while (true)
    {
        while ((r1[++i] < pivot) && (i < end));
        while ((r1[--j] > pivot) && (j > begin));
        if (i >= j) break;
        swap(r1[i], r1[j]);
        swap(r2[i], r2[j]);
    }
    r1[begin] = r1[j];
    r1[j] = pivot;
    r2[begin] = r2[j];
    r2[j] = r2pivot;
    quicksort(begin, j - 1);
    quicksort(j + 1, end);
}
int main() {
    int x1, y1, x2, y2; cin >> x1 >> y1 >> x2 >> y2;
    int N;
    cin >> N; for (int i = 0; i < N; i++) {
        int xn, yn; cin >> xn >> yn;
        x[i] = xn; y[i] = yn;
        r1[i] = sqrt(sqr(xn - x1) + sqr(yn - y1));
        r2[i] = sqrt(sqr(xn - x2) + sqr(yn - y2));
    }
    quicksort(0, N-1);  //this modified quicksort will sort r1&r2 together according to r1. r2 won't be monotone, 
                        //but r1[i] and r2[i] will record the distance to two towers of the same node. 
    r2max[N - 1] = r2[N - 1]; //r2max[i] means: the max value between r2[i]~r2[N-1]
    for (int i = N - 2; i >= 0; i--) r2max[i] = max(r2max[i + 1], r2[i]);
    double ans = sqr(r2max[0]);
    for (int i = 0; i < N; i++) {
        ans = min(ans, sqr(r1[i]) + sqr(r2max[i + 1])); 
    }
    cout << (int)ans;
}
```

## CET-6 Words

### 题意概述

给出n个长度不超过10的字符串，$2\leq n \leq 50000$，每个字符串只含英文小写字母。求出最长的，出现至少两次的前缀与后缀，以及它们的出现次数。

依次按照下列规则选择唯一答案：

1. 最大长度
2. 最大出现次数
3. 最小字典序

题目保证没有完全相同的字符串。

Spec: 1000ms, 256MB

### 算法 

Tags: 哈希

建立两个哈希表用于查找并记录重复子串。由于字符串长度不超过10且只有小写字母，可以用0-25的数字（5bit）表示每个字符，用一个`long long int`表示一个字符串。

选用拉链法处理哈希冲突。哈希函数$H(n)=H(n-1)*7919+input(n)$。实测输入50000个随机字符串，冲突次数不超过8次。

时间复杂度$O(n)$，空间复杂度$O(hash\_size)$

### 代码

```cpp
#include <iostream>
#include <cstring>

const int HASH_SIZE = 2 << 16, HASH_PRIME = 7919;
const int DEFINE_LEN = 1;

template <typename T>
class List
{
public:
    struct Node
    {
        long long val;
        Node* next;
        int count;
    };
    void deleteNode(Node* me)
    {
        if (me == nullptr)
            return;
        deleteNode(me->next);
        delete me;
    }
    List();
    ~List();
    Node* head, * tail;
    int len;
    int push_back(long long);
    void clear()
    {
        deleteNode(head);
        head = tail = nullptr;
        len = 0;
    }
};

template <typename T>
List<T>::List()
{
    head = tail = nullptr;
    len = 0;
}

template <typename T>
List<T>::~List()
{
    deleteNode(head);
    len = 0;
}

template <typename T>
int List<T>::push_back(long long _op)
{
    //long long _op = 0;
    //for (int i = 0; i < op.length(); i++) _op = _op * 26 + (op[i] - 'a');
    if (tail == nullptr)
        head = tail = new Node;
    else
    {
        Node* tmp = head;
        for (; tmp != nullptr; tmp = tmp->next)
            if (tmp->val == _op)
            {
                tmp->count++;
                return tmp->count;
            }
        tail->next = new Node;
        tail = tail->next;
    }
    tail->val = _op;
    tail->next = nullptr;
    tail->count = 1;
    len++;
    return 0;
}

std::string str[50005];
List<std::string> prehash[HASH_SIZE + 5], sufhash[HASH_SIZE + 5];
std::string longest_prefix;
int N = 0, longest_prefix_len = 0, longest_prefix_count = 0;
std::string longest_suffix;
int longest_suffix_len = 0, longest_suffix_count = 0;

int main()
{
    std::cin >> N;
    for (int i = 0; i < N; i++)
        std::cin >> str[i];
    for (int i = 0; i < N; i++)
    {
        int pre_hashval = 0, suf_hashval = 0, len = str[i].length();
        char prebuf[15] = { 0 };
        long long prebufhash = 0;
        for (int j = 0; j < len; j++)
        {
            prebuf[j] = str[i][j];
            pre_hashval *= HASH_PRIME;
            pre_hashval += str[i][j];
            pre_hashval %= HASH_SIZE;
            prebufhash = prebufhash * 32 + (prebuf[j] - 'a');
            if (j < DEFINE_LEN)
                continue;
            if (int count = prehash[pre_hashval].push_back(prebufhash))
            {
                if (j >= longest_prefix_len)
                {
                    if (j > longest_prefix_len)
                    {
                        longest_prefix_len = j;
                        longest_prefix_count = count;
                        longest_prefix = prebuf;
                    }
                    else if (count > longest_prefix_count)
                    {
                        longest_prefix_count = count;
                        longest_prefix = prebuf;
                    }
                    else if ((prebuf < longest_prefix) && (count == longest_prefix_count))
                        longest_prefix = prebuf;
                }
            }
        }
        //-------------------------------------
        char sufbuf[15] = { 0 };
        long long sufbufhash = 0;
        for (int j = len - 1; j >= 0; j--)
        {
            for (int k = 0; k < len - j; k++)
                sufbuf[k] = str[i][k + j];
            suf_hashval *= HASH_PRIME;
            suf_hashval += str[i][j];
            suf_hashval %= HASH_SIZE;
            sufbufhash = sufbufhash * 32 + (str[i][j] - 'a');
            if (j >= len - DEFINE_LEN)
                continue;
            if (int count = sufhash[suf_hashval].push_back(sufbufhash))
            {
                if (len - j >= longest_suffix_len)
                {
                    if (len - j > longest_suffix_len)
                    {
                        longest_suffix_len = len - j;
                        longest_suffix_count = count;
                        longest_suffix = sufbuf;
                    }
                    else if (count > longest_suffix_count)
                    {
                        longest_suffix_count = count;
                        longest_suffix = sufbuf;
                    }
                    else if ((sufbuf < longest_suffix) && (count == longest_suffix_count))
                        longest_suffix = sufbuf;
                }
            }
        }
    }
    std::cout << longest_prefix << ' ' << longest_prefix_count << '\n'
        << longest_suffix << ' ' << longest_suffix_count;
}
```

## Queue at dining hall

### 题意概述

N个学生正在排队，$N\leq 500000$, 他们的身高不超过$1*10^8$。若两个学生之间的所有学生身高比他们中较矮的更矮或相同，则称这两个学生能互相看到对方。求所有能互相看到对方的学生数。

Spec: 1000ms 256MB

### 算法 

Tags: 模拟, 栈

遍历排队学生，构建一个栈存放身高。维护栈中元素的非严格递减性：先将小于当前学生身高的元素全部弹出，并计数；计数与当前身高相同的学生人数；最后将当前学生身高压入栈。

算法模拟的是朴素的计数方法：对于某一个学生，他能看到在自己之前的第一个比自己高的学生（挡住了更前面的所有学生），以及所有在自己之前的、身高非严格递减且不高于自己的学生（特别矮的被挡住了）。

时空复杂度都是$O(n)$。

### 代码
```cpp
#include <iostream>
struct {
	int height, count;
} lowering_stack[500005];
int stack_ptr;
int main() {
	int N;
	std::cin >> N;
	int ans = 0;
	std::cin >> lowering_stack[0].height;
	lowering_stack[0].count = 1;
	stack_ptr = 0;
	for (int i = 1; i < N; i++) {
		int user_inp; std::cin >> user_inp;
		while ((stack_ptr >= 0) && (lowering_stack[stack_ptr].height < user_inp)) {
			ans += lowering_stack[stack_ptr].count;
			stack_ptr--;
		}
		if(stack_ptr<0) {
			stack_ptr++;
			lowering_stack[stack_ptr].height = user_inp;
			lowering_stack[stack_ptr].count = 1;
		} else {
			if (user_inp == lowering_stack[stack_ptr].height) {
				ans += lowering_stack[stack_ptr].count;
				lowering_stack[stack_ptr].count++;
				if (stack_ptr > 0) ans += lowering_stack[stack_ptr - 1].count;
			}
			if (user_inp < lowering_stack[stack_ptr].height)  {
				ans++;
				stack_ptr++;
				lowering_stack[stack_ptr].height = user_inp;
				lowering_stack[stack_ptr].count = 1;
			}
		}
	}
	std::cout << ans;
}
```

## 全部Tags

枚举, 排序, 递推, 哈希, 模拟, 栈