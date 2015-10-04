---
layout : post
title : "Berrick “An approach to algebraic K-theory”一书TeX排版缘起"
category : K-theory
date : 2015-09-11
tags : [LaTeX，K-theory]
SyntaxHihglighter: true
shTheme: shThemeDefault 
duoshuo: true 
math: true
---

## 缘起

 在读一些文章和书时，参考文献中出现了Berrick的这本书*An approach to algebraic K-theory*。Google和Baidu之后都没能找到这本书，继而发邮件询问了Feng Ji师兄，后来从Shengkui Ye师兄那里得到了一份扫描版的.djvu文件。简单浏览之后发现这本书是不可多得的简介，在短短百余页介绍了很多东西，放在现在也是值得参考的文献，之后便想把扫描版的书籍转化成电子版，于是便有了现在这个项目。

## 回忆

拿到这本书的电子版也是很幸运的。时光追溯到刚念研究生时：第一天报道当晚接到了ZQ师兄的电话，通知第二天去首都机场接机。第二天上午接到的第一位便是上面所说的Feng Ji师兄。记得Ji师兄说等Ye师兄来了介绍给我们，说他社交很广，认识的人很多。后来有幸见到叶师兄作报告，却没有机会聊聊。

世间有很多的奇迹，也有很多的巧合。在一次上完课后，和Yang Su老师聊天，聊起来想学的一个东西，就提起了Ye师兄，说他对这块比较熟悉，后来果然看到了Ye师兄写的一篇相关的文章，也看到了和Su老师合作过的一篇论文。更巧合的是在今年暑假和王向军老师闲聊时，才知道王老师和新加坡国立的几个老师都非常熟悉。王老师还讲了一件有趣的事，本来他已经买了去新加坡的机票，后来一想在新加坡抽烟是要施以鞭刑的，王老师说自己怕烟瘾犯了到时候万一被抽两鞭子划不来，于是又把机票退了。和王老师还聊了很多有趣的故事，真是时间过得飞快，不知何时还能陪王老师把酒畅谈？

## 进度

回到这个文档，在拿到扫描文档后我便开始了行动。最开始一个字一个字打完了前言，发现效率实在太低，险些有些产生放弃的念头。接下来完成了第九章，因为正好在看相关的内容。突然有一天想到是否可以用OCR识别软件来识别英文呢？由于扫描版印刷并不是很清晰，使用软件后很多字符还是有错误，但好在省去了很多打“字”的工作，于是这个tex版本的文档也相当于“校对”版本，主要是把一些公式和图表打出来。尽管如此，还是花了一些功夫，快半年了也快到了收尾的时候。收尾并不轻松，参考文献和索引需要核对，交叉引用也需要设置，尽量把编号和原文一致。但也由于自己水平的限制，许多内容相信还是有些错误，如果发现这些错误那么都是因为我的不认真导致的。

2015年10月5日更新：完整版第一个版本现在已经上传到github，欢迎学习。

----

最后，摘部分原书的前言作为本文的结尾：

> Two decades ago, the term “algebraic K-theory” had not even been born --- the subject was still in embryo. A decade later, there was no doubt of existence; it was uniqueness which seemed at risk as seemingly distinct competing definitions tumbled forth. Since then there has been much reconciliation and development. It is now unquestionably a subject in its own right, clearly flourishing.  

    
>  Yet in certain respects it has grown too fast. The wider mathematical community had found it hard to keep up with the pace, as anyone trying to find the AMS (1980) classification for the subject will appreciate. (There has, however, been significant acknowledgement of its achievements, most notably in the award of a 1978 Fields Medal to one of its exponents, D. Quillen.) In particular,  it has become very difficult for “outsider” (whether established Mathematicians in other areas, or graduate students wishing to enter the fray) to gain access to the material which must be mastered before current research can be studied. Nobody has written an introduction to the subject since its quite early days. A new one is sorely needed. In addition, Quillen's fundamental tool for the most-travelled path to higher algebraic K-theory, the plus-construction, now receives attention from geometric topologists and homotopy theorists. Again, there is a place for a thorough, up-to-date treatment of the basics. 

> This book is a modest attempt to meet those needs. In 1976 I gave an eight-lecture graduate course at Oxford, much of its content deriving from (a small portion of) a course Quillen delivered at M.I.T. while I was visiting there in 1974--1975. The next few years saw a number of developments, so that by 1981 a repeat course at Oxford comprised sixteen lectures. These now constitute the core of the book, although the inevitable inflation has resulted in only one chapter(the eighth) resembling lecture-sized length. 

> I have in mind as likely reader an algebraist, topologist or algebraic number-theorist requiring first of all a little motivation before confronting the technicalities. The first three chapters therefore emphasize the history of the topic and its relationship to its “older sibling”, topological K-theory. In chapter 4 the real work begins, in the shape of an introduction to the plus-construction. There is, alas, no escaping the reader's need for a little topological familarity here, but I have tried to minimize this. The pleasent surprise is how much algebra, in the form of fundamental group-actions on homotopy and homology groups, lies at the heart of this approach. As a result, the discussion (in Chapter 9 and 11) of seemingly topological properties of the topological space $BGL(A)^+$ is in large part algebraic. For me, an especially satisfying aspect of the treatment is the way in which the same lemma(3.11) in homology of groups is revealed as lying behind both the de-looping of $BGL(A)^+$ in chapter 11 and the passage from equivariant $A$-representations to $KA$-theory exploited in Chapter 12 and 13. 

> Throughout I have tried to complement, rather than reproduce, established references. K-theory veterans, as well as novices, should therefore find something here to interest them. By making the plus-construction the central theme of the work, I have automatically ruled out chances of definitiveness: some results which I state for completeness' sake have been established by quite different methods. The reader should be aware that this is only an approach to the subject. I hope it encourages him/her also to contemplate others. 
