---
title: DKS3 Fundamentals and Skills
---

Written by Aether.

作者：Aether

A brief, although accurate, account of the core PvP gameplay mechanics and skills used for successful play.

本文档是对黑暗之魂III的核心PVP玩法、技巧及机制的精要介绍。

This document essentially explains at the basic level of why certain strategies are effective and others are not and why the game&#39;s meta and balance is asymmetrically skewed. It also, hopefully, provides a more concrete resource for players looking to improve their understanding of the mechanics and their skills.

本文档将介绍所有重要的游戏机制，并探讨如下两个问题：为何特定对战策略是有效的而另一些不是；为何meta武器（火麒麟）和常规武器之间的强度差距如此之大。本文希望能够为读者提供可靠而有价值的信息，以便读者决定自己的对战策略、提升自己的游戏水平。

This refers specifically to 1v1 PvP, although all of the outlined mechanics are applicable to every form of PvP.

本文是为决斗玩家写的，尽管提到的所有机制对入侵等玩法也都适用。

# Fundamentals 基础

## Spacing 卡距离（小走位）

Avoiding an attack without rolling or blocking, but can also refer to attacking in a way that makes it harder for your opponent to space you.

这个词一般指的是，在不翻滚或防御的前提下避开一次攻击。但有时它也可以用于形容一种进攻策略：让对手更难走位绕开你的攻击。

Spacing is highly advantageous because avoiding an attack without needing to roll, block or perform any other committal action leaves you in the optimal position to punish your opponent, as you are not in recovery or in hitstun.

卡距离是非常有价值的策略。不翻滚、防御或做其他动作就避开对手的攻击，能给你更好的站位和时机来反击/惩罚对手，毕竟你不在前后摇或受击硬直中而对手正处于硬直中。

If an attack cannot be spaced, for any reason, the safest option is to roll or block it, depending on the context.

如果对手的攻击不便卡距离，最安全的选择就是滚开或者挡住，根据战况而定。不要过度沉溺于卡距离的意图中。

Because of client side hit detection, increasing latency will make attacks appear to have more range than they visibly do. In these scenarios, spacing in anticipation of an attack is required. On lower latencies, spacing can be performed on reaction to most attacks.

因为魂3的攻击判定机制（国内有个相关说法，模型残留），高延迟会让对手的攻击距离比看起来远。这时候靠预判来卡距离就比较重要了，然而在低延迟时，只靠观察对手攻击后再反应，就能完成绝大多数卡距离进攻。

## Timing

这个词比较难翻译，大致意思是协调自己的攻击时间、前后摇与对手的行动，从而反击或封出手，防止被对手反击或封出手等。下文称为&quot;卡时间&quot;，请读者理解。

Timing refers to anything that must be appropriately timed to be successful, such as a reaction roll, whiff punish or a rollcatch.

卡时间指的是任何在正确时机进行才有价值的操作，如看滚、确认反击或抓滚。

Most attacks in Dark Souls 3 are consistently reactable, with a very small minority of moves being genuinely unreactable or hard to react to. Reaction rolling is performing the roll input at the correct timing to avoid an attack.

魂3中，绝大多数玩家动作都没有快到不能反应，只有极少数动作几乎不能或很难反应（比如小镰刀！）。看滚，在正确时机翻滚来回避一次攻击，就是这种策略的一个典型例子。

Most players typically develop reaction rolling as a skill later than spacing because it requires a (very minor) conscious input whereas spacing is usually done mostly on autopilot.

大部分玩家是在学会卡距离后系统性地学会看滚的，毕竟在对局中翻滚所用的时间和思考时间远小于卡距离——卡距离某种意义上说是贯穿整个对局中的操作，而看滚不是。

When an opponent commits to an action, such as a roll or an attack, the animation has a set period of recovery frames until they can perform another action, such as a roll. This is the player&#39;s window to attack the opponent before they can roll or attack you in turn. The ability of a player to whiff punish is typically determined by whether or not their weapon is fast enough to be able to punish a recovery. This can be determined by simply comparing the recovery of the opponent&#39;s animation to the startup of your attack.

当对手进行一次行动，比如翻滚或攻击后，他的人物会获得一段硬直（国内把这个硬直细分为前摇+生效帧+后摇），在这段硬直内他不能更改动作或做出其他动作。这正是读者攻击他而他无法对你的攻击做出其他反应的最佳时间段。读者能否确认反击对手（惩罚对手的空挥），主要取决于读者手上的武器是否足够快。从数据上看，把武器前摇和对手的硬直长度比较一下就行———在格斗游戏玩家群体中，似乎有&quot;有利帧&quot;这种类似的说法。

While rollcatching with the vast majority of weapons and attacks requires an opponent to be unable to reaction roll a reactable move, some attacks such as certain R2s can be released on reaction to a roll while charging them. Some neutral R1s and projectiles can also be timed on reaction to an opponent&#39;s roll.

对于大部分武器而言，抓滚只在对手看滚失误或者瞎滚的时候有用；相比之下有些武器的蓄力r2用起来更方便些。不过，也有少部分武器的r1以及部分远程攻击，例如小镰刀和小曲等，快到能够在确认对手翻滚之后抓滚。这些攻击相对来说有很大的抓滚压力。

A backswing is a type of rollcatch that cannot be avoided regardless of reactions. This is when one attack recovers extremely quickly into a consecutive attack. The first attack forces a roll response from the opponent, and because it recovers fast enough into a consecutive move, this is guaranteed to hit the opponent during roll recovery. Backswings are most effective at close range, near walls and corners. Only certain weapons have the frame data to facilitate backswings, and the success rate of backswings is latency dependent.

_在翻译这段之前需要解释一个重要的词： __backswing__ 。国内部分成熟的直剑玩家可能已经意识到，在时机和距离合适的时候连挥长直剑特别是对剑，对手必定会被第二下 __r1__ 打中。 __Backswing__ 就是指这种动作，下文将会牵强地翻译成连挥，请读者理解。_

连挥是一种特殊类型的抓滚，对手无论如何都不可能躲开。具体地说，如果一个武器的某种动作可以很快地打两下，那就有机会完成这种进攻。对手将被迫翻滚躲开读者的第一下攻击，而第二下攻击会卡在对手的翻滚后摇内，必定命中对手。连挥在近距离和压板时特别有效。只有少部分武器的攻击模组能够完成连挥，而且足够低的延迟也很重要。关于延迟对无敌帧的影响（高延迟会增强无敌帧），可以参见转载至B站的Amir.的研究视频。

# Auxiliary Fundamentals 其他重要机制

## Backstabs 背刺

Backstabs are mostly a subsidiary of spacing, however understanding how they function mechanically will allow the player to counter and avoid them.

一般来说，背刺是卡距离的一个分支。不过，专门学习一下背刺机制有助于读者回避和反击敌方的背刺意图。

Behind the player&#39;s back is a &quot;cone&quot;, where performing an R1 input will initiate a backstab grab attempt. After the backstab grab has been initiated, anything in range of the backstab grab, regardless of its orientation, will be pulled into a successful backstab.

在每个玩家的背后有一块扇形区域（其实是长方形），敌方在这个区域内的r1会变成一个背刺起手。当对手的背刺吸力启动后，如果玩家还处于这个区域内就会被吸回去。

All backstabs can be avoided through iframes.

背刺动作可以通过无敌帧来回避，也就是说无敌帧内背刺吸力是无效的。

Some attacks have long enough recovery to be rolled past and then backstabbed, however this is a minority. Most attacks have low enough recovery that attempting to roll past them is punishable.

少数慢速武器的攻击动作后摇太大，可以完成翻滚背刺；但绝大多数的武器后摇都没那么大，如果对手试图翻滚过去，读者是可以抓对手滚或者刮一下的。

## Match-up knowledge 如何消除信息差

Match-up knowledge refers to understanding the dynamic between your weapon and your opponent&#39;s. Understanding the different properties of all of your opponent&#39;s potential attacks is required to have an effective matchup knowledge.

信息差是形容一个玩家与他的对手的游戏理解深度之差异的，这种差异主要在于对武器动作和性能的熟悉程度上，但也包含一些机制和数据相关的知识。众所周知，理解对手可能做出的全部行动的细节，是进行一次高质量对局必备的。

Key points of matchups to be aware of are (in no particular order):

下面列举一些需要知道的关键信息（不分先后次序）：

- Hitstun
- 受击硬直
- Tracking
- 追踪性
- Range
- 范围
- Hyper armour startup, poise health, poise damage.
- 霸体启动速度，霸体值与韧性，削韧
- Recovery
- 硬直/前后摇
- Frame advantage/disadvantage
- 有利帧/不利帧

The difference in the time it takes for you to recover from your attack and the time it takes for your opponent to recover from hit stun or block stun is called frame advantage.

攻击者的攻击后摇与对手防御/受击的硬直长度之差，被称为有利帧（或者不利帧）。

Frame advantage can be represented as a positive or negative number to indicate who recovers first after the move is executed, although this is typically not required in Dark Souls 3.

有利/不利帧数可以用正或负数来表示，不过这个在格斗游戏那边比较流行，在魂3这边帧数据价值不是很大。

Due to Dark Souls 3&#39;s linear hitstun system, understanding frame advantage is very simple.

由于魂3的受击硬质系统是线性的（非常朴素），理解有利帧这个概念不怎么难。

If you and your opponent trade at the exact same time, the player hit by an attack with more hitstun will recover later and therefore likely be frame disadvantaged. If both players&#39; attacks dealt the same amount of hitstun, the player with a slower weapon will be frame disadvantaged.

如果读者和0延迟对手在完全相同的时刻拼刀，谁的受击硬直更大谁就吃亏，比如小曲拼直剑。如果双方受击硬直相同，谁的武器攻速快谁就有利。

In a scenario where you are frame disadvantaged, the safest course of action is to roll or block instead of attempting to attack.

如果读者处于不利帧中，应该立刻准备翻滚或格挡，尽量不要反打。

## Swapping

在战斗中切换武器戒指衣服等，下文称为速切

Entering the inventory to change equipment rapidly is a strategy used by players. The common form of equipment swapping is ring swapping, where players change rings depending on the matchup present or the stage in the fight. This allows players to reap various statistical benefits from rings during a fight, rather than only the statistical benefits they started with.

速切这个玩法是指迅速打开菜单并换武器或装备。最有价值的速切玩法是切戒指，这能给玩家带来许多战术和数据上的优势。

Ring swapping is not a required skill to be proficient, but is very advantageous and every player can benefit from it, regardless of playstyle.

切戒指并不是上流玩家必备的技巧，但它很有用而且很好学，无论读者是什么风格的玩家它都能有所帮助。

_真的有上流玩家不会切戒指吗☹_

Weapon swapping is a form of equipment swapping where players change weapons during a fight in order to surprise the opponent or gain access to situationally more advantageous attacks. For example, if using a weapon that doesn&#39;t have hyper armour, a player may quickly swap to a weapon that has fast hyper armour startup and catch the opponent off guard with a trade.

切武器/武器库则是指，在对局中打开菜单切换自己的武器，来做出对手意料之外的进攻或改善战况。常见的玩法有切枪跑攻或者切个霸体武器拼刀，等等。

Weapon swapping in this context is highly flawed as it mostly relies on the opponent&#39;s inability to react and modify their approach to what you have swapped weapons to.

事实上切武器玩法完全没价值，因为它基本上依赖对手太菜而不能反应/适应读者切出的新武器。高水平对局里依赖对手的低级错误或者弱点是不可取的。

_个人认为少部分切武器玩法还是有相当价值的，比如拼刀切匕首或者忍耐等等。 __Aether__ 说的比较极端_

An exception to this is swapping weapons after a parry or guard break. In this situation, players can swap to a weapon that deals high critical damage, in order to maximise riposte damage output. This form of weapon swapping is used purely to gain a statistical damage increase. It is also highly safe as the opponent cannot punish it due to being in the riposte state.

有一个特例就是弹切。（省略）

Another effective application of weapon swapping is when the opponent is getting up from a backstab or riposte. Some weapons have attacks that are difficult to avoid on wakeup, such as backswings. In this context of weapon swapping, the user is maximising their chances of landing damage on wakeup, and is also safe to do so as the opponent is transferring from the wakeup animation into a roll.

另外一个特例是切武器压起身。（省略）

Weapon swapping is also not a required skill to be proficient, but can have benefits when used situationally.

切武器这玩法也不是成为上流玩家必要的，不过学了经常也能有点用。

# Other skills 其他技巧

## Prediction 预判

Contrary to popular belief, prediction is not a fundamental skill in Dark Souls 3 as it is not required for success or optimal play in all matchups.

与很多玩家所认为的不同，预判敌方行动并不是在魂3PVP中重要的技巧之一。即使不会预判也能够进行高质量的对局。

However, some matchups will require players to rely upon prediction to win. Typically, weapons that can be consistently avoided on reaction or weapons that lack the capacity to punish recoveries on reaction must rely upon prediction to be successful.

然而有些对局玩法比较依赖玩家的预判，特别是在用可以看滚的慢速武器时。如果一个武器没有任何快速动作，那它就得靠预判来玩了。

Prediction is highly inconsistent as it relies on interpreting behavioural clues about your opponent&#39;s patterns in order to inform your decision to perform an action or not. An inaccurate read is typically punishable.

预判这个策略是非常不稳定的，因为读者必须试图解读对手的行动和策略，而如果你读错了对手往往可以轻易惩罚/反击你。不靠预判而只靠压力和连挥等可靠的技巧才是稳妥的打法。

The extent to which prediction is required for success in certain matchups is proportional to the amount of latency present.

预判这个策略的有效性与对局双方延迟成反比。

_这段内容见仁见智吧_

# Fundamental Design Flaws 一些致命的游戏设计问题

Dark Souls 3&#39;s weapon balance is essentially an asymmetrical pyramid, where the strength of a weapon is governed almost entirely by whether or not it can be avoided on reaction. The privileged minority of weapons that cannot be avoided on reaction are distinctly advantaged compared to everything else.

魂3的各种武器的pvp强度，大致上而言可以排列成金字塔型。某个武器的强度基本上只跟它的攻速，或说难以看滚的程度有关。小曲匕首等等快速武器的强度几乎碾压了其他武器。

What differentiates good from bad is whether a weapon can be consistently avoided on reaction with a roll. Unreactable attacks or backswings cannot be consistently avoided on reaction, therefore making them viable when used offensively.

如果一个武器难以持续看滚，它就是有强度的；或者对剑等较容易完成连挥的武器。也就是说，只有有理由能够击中对手的武器才是有强度的。

The vast majority of attacks in Dark Souls 3 can be avoided on reaction with 100% consistency.

大多数武器都能持续稳定看滚。

As a result, the only reliable way to land these attacks in 1v1 at the top level is either:

因此最高水平的对局里只有两种策略是有效的：

- For the opponent to commit to an action
- 在对手的硬直中攻击他，例如卡距离，卡时间或连挥
- For the opponent to have poor spacing
- 让对手出现一个距离判断错误

These weapons or attacks are generally considered not viable at the top level of play, as they have no counterplay to an opponent simply playing defensively, due to relying on the opponent attacking or performing an action first in order to land damage.