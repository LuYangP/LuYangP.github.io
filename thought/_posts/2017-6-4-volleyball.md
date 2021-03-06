---
layout: post
comment: on
title: 垫排球的数学期望
mathjax: true
---

今年开春，池塘边的柳树染上一种怪病，叶片枯黄，树皮剥落，眼下十几棵竟都死绝了。从此熟悉的小路上再看不到柳絮飘拂，我少有地惶恐起来。害怕春天不再是春天，秋天不再是秋天，夏天不再炎热，冬天不再寒冷。所有的东西还来不及凭吊就已灰飞烟灭。

<!--excerpt-->

一时想起很多过去的事儿。记得我曾经挺喜欢玩排球，但是已拿不准到底是为了准备中考体育才喜欢排球的，还是真的喜欢。如同我已拿不准是不是为了语文考试才喜欢上看书的。反正现在我只喜欢玩电脑，一点都不喜欢看书。

说起中考体育，排球这东西可是最靠运气的。据我观察，大多数人稍加练习很快都能达到满分水平，可在考场能不能拿到满分，完全得看老天爷的脸色。不管你垫到第几个，突然间妖风一起，这次机会就算告吹。真有不少人上阵连遇三股妖风，别的科目测都没测，直接办了缓考。

诸君，要知道任何时间、任何地点都有可能刮起妖风，所以啊，不管您练习得多么刻苦，单次垫球成绩也依然是一到十之间的均匀分布。这样单次垫球的数学期望不难计算，为

$$ \frac {1 + ... + 10} {10} = 5.5 $$

有趣的是，中考排球总共有三次垫球机会，取最好的一次作为最终的成绩。那么，三次机会较一次机会将如何改变总体的数学期望呢？

设三次垫球的成绩分别为$X_{1}$、$X_{2}$、$X_{3}$，随机变量$X_{i}$取1到10之间的整数，且均匀分布。

最终成绩$M$，为$$max\{X_{1}, X_{2}, X_{3}\}$$，取值也是1到10之间的整数。$M$取某一整数$k$的概率为

$$P(M=k)=P(max\{X_{1}, X_{2}, X_{3}\}=k)$$

此概率不便直接计算，故转而计算$M$的累积分布函数

$$ P(M \leqslant k) = P(max\{X_{1}, X_{2}, X_{3}\} \leqslant k)=P((X_{1} \leqslant k) \cap (X_{2} \leqslant k) \cap (X_{3} \leqslant k))$$

由于$X_{1}$、$X_{2}$、$X_{3}$三个随机变量相互独立，故

$$P(M \leqslant k)=P(X_{1} \leqslant k) \cdot P(X_{2} \leqslant k) \cdot P(X_{3} \leqslant k)$$

而$$P(X_{i} \leqslant k)= \frac {k} {10} $$，所以$$P(M \leqslant k)=\frac {k^3} {1000}$$

$$P(M=k) = P(M\leqslant k) - P(M\leqslant (k-1))= \frac {k^3 - (k-1)^3} {1000}$$

$$E[M] = \sum_{k=1}^{10} k P(M=k) = \sum_{k=1}^{10} \frac {k(k^3 - (k-1)^3)} {1000} = 7.975$$

可见，三次机会使得排球成绩的数学期望从5.5上升到7.975。
