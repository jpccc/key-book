# 钥匙书 Key-book

周志华、王魏、高尉、张利军等老师所著的**《机器学习理论导引》**一书（下称《导引》），填补国内缺少机器学习理论入门著作的遗憾。该书试图以通俗易懂的语言，为有志于学习机器学习理论和研究机器学习理论的读者提供一个入门的导引。《导引》主要涵盖七个部分，分别对应机器学习理论中的七个重要概念或理论工具，即：**可学性、（假设空间）复杂度、泛化界、稳定性、一致性、收敛率、遗憾界**。

《导引》是一本理论性较强的书籍，涉及大量的数学定理和各种证明。尽管撰写团队已尽可能降低了难度，但由于机器学习理论学习本身的特性，该书仍然对读者的数学背景提出了较高的要求。这难免会导致不求甚解的情形，影响学习效果；另一方面，由于篇幅所限，该书写作较为精炼，并非在各个章节都给出示例。读者每每遇到晦涩抽象之处，难免冥思苦索。

基于此两点，我们决定尝试编辑《钥匙书》这一参考笔记，来对《导引》一书作一些浅陋且皮毛的注脚。这既是着眼于那些阅读《导引》时遇到困难的读者，助其更快地走出迷雾；亦是对学习《导引》一书之过程的最好记录。

## 使用说明

- 《钥匙书》的补充性工作，主要包括四个方面：

  （1）**证明补充**：对部分证明的证明思路进行解释，对部分省略的证明过程进行补充。

  （2）**案例补充**：增加解释案例，帮助读者理解。

  （3）**概念补充**：介绍部分文中涉及、但未阐释的概念。

  （4）**参考文献讲解**：对部分重要的参考文献进行介绍。

  此外，由于《导引》一书的第一章节为基础知识补遗，简明易懂，因此《钥匙书》的内容从《导引》的第二章开始。

### 在线阅读（内容实时更新）
地址：https://datawhalechina.github.io/key-book/



### 目录

- 第1章 [绪论](https://datawhalechina.github.io/key-book/#/chapter1/chapter1)
- 第2章 [可学性](https://datawhalechina.github.io/key-book/#/chapter2/chapter2)
- 第3章 [复杂度](https://datawhalechina.github.io/key-book/#/chapter3/chapter3)
- 第4章 泛化界
- 第5章 稳定性
- 第6章 一致性
- 第7章 收敛率
- 第8章 遗憾界
- 第9章 总结

### 选用的《机器学习理论导引》版本

<img src="https://raw.githubusercontent.com/datawhalechina/key-book/master/res/mlt.jpg" width="150" height= "175">

> 版次：2020年6月第1版<br>

## 编委会
| 职责 | 名单 |
| :---: | :---: |
| **主编** | [@HaoZHAN](https://github.com/zhanhao93) |
| **编委** | [@MaolinWANG](https://github.com/mlw67) [@leafy-lee](https://github.com/leafy-lee) [@YiwenYANG](https://github.com/youngfish42) [@Sm1les](https://github.com/Sm1les) |



## 关注我们

<div align=center>
<p>扫描下方二维码，然后回复关键词“钥匙书”，即可加入“钥匙书读者交流群”</p>
=======
# 《机器学习理论导引》NOTES
---

## 第一章：序言

*Edit: Hao ZHAN*

*Update: 06/08/2020*

---

## 1.关于《机器学习理论导引》

近年来，机器学习备受关注，机器学习的相关课程与教材可谓汗牛充栋。就国内教材而言，周志华的**《机器学习》**和李航的**《统计学习方法》**已然成为了广大学子入门机器学习的宝典。而 Mitchell 的 ***Machine Learning***， Duda 等人的 ***Pattern Classification***， Alpaydin 的 ***Introduction to Machine Learning***，则提供了一些古典风格的路径选择。若有更深入的需求， Bishop 的 ***Pattern Recognition and Machine Learning***， Murphy 的 ***Machine Learning - A Probabilistic Perspective***，Hastie 等人的 ***The Elements of Statistical Learning***，则可以系统性地给学习者提供帮助。以上的这些书籍还仅仅是广大学习材料中的一隅，似乎可以说无论国内精品，亦或海外译丛，都已不再缺乏。

然而，若是以**机器学习理论**的视角来考察国内的学习材料，则可以得出不同的结论。与上述描述机器学习算法（Machine Learning Algorithm）的著作不同，关注机器学习理论（Machine Learning Theory）书籍似乎并没有得到多少讨论。尽管在上述的这些著作中，或多或少都展开了对于理论的探讨，但篇幅极为有限——或为些许独立篇章，或为一点只言片语，难以满足广大学子理论学习、研究之渴求。

过去，机器学习理论的经典教材多以英文写作。上世纪末，围绕统计学习理论所展开的一系列讨论，产出了诸多经典文献。较为著名的有 Vapnik 的 ***The Nature of Statistical Learning Theory*** 和 ***Statistical Learning Theory***，以及 Devroye 等人的 ***A Probabilistic Theory of Pattern Recognition***。一些近期的讨论则是来自于 Shalev-Shwartz 和 Ben-David 的 ***Understanding Machine Learning***，以及 Mohri 等人的 ***Foundations of Machine Learning***。尽管 Vapnik 的两本著作，以及 ***Foundations of Machine Learning*** 都已有了优质的译作，但以中文来写作的、属于我们自己的机器学习理论入门著作的缺乏，仍旧是一个不大不小的遗憾。

而现在，周志华、王魏、高尉、张利军等老师所著的**《机器学习理论导引》**一书（下称《导引》），则填补这个空白。该书试图以通俗易懂的语言，为有志于学习机器学习理论和研究机器学习理论的读者提供一个入门的导引。该书主要涵盖七个部分，分别对应机器学习理论中的七个重要概念或理论工具，即：**可学性、（假设空间）复杂度、泛化界、稳定性、一致性、收敛率、遗憾界**。

学习机器学习理论虽不如学习机器学习算法那样，可以立即将所学付诸应用。但只要砥砺前行、深入学习，则不仅可领悟机器学习中的重要思想，亦可体会机器学习之奥妙。[1]   

## 2.关于《机器学习理论导引》NOTES

《导引》的NOTES，在团队内部又被戏称为《钥匙书》。《钥匙书》一名，取自《导引》一书的戏称——《宝箱书》，暗含抱关执钥，助诸位读者解惑之意。《导引》是一本理论性较强的书籍，涉及大量的数学定理和各种证明。尽管撰写团队已尽可能降低了难度，但由于机器学习理论学习本身的特性，该书仍然对读者的数学背景提出了较高的要求。这难免会导致不求甚解的情形，影响学习效果；另一方面，由于篇幅所限，该书写作较为精炼，并非在各个章节都给出示例。读者每每遇到晦涩抽象之处，难免冥思苦索。

基于此两点，我们决定尝试编辑《钥匙书》这一参考笔记，来对《导引》一书作一些浅陋且皮毛的注脚。这既是着眼于那些阅读《导引》时遇到困难的读者，助其更快地走出迷雾；亦是对学习《导引》一书之过程的最好记录。

《钥匙书》的补充性工作，主要包括四个方面：

（1）**证明补充**：对部分证明的证明思路进行解释，对部分省略的证明过程进行补充。

（2）**案例补充**：增加解释案例，帮助读者理解。

（3）**概念补充**：介绍部分文中涉及、但未阐释的概念。

（4）**参考文献讲解**：对部分重要的参考文献进行介绍。

此外，由于《导引》一书的第一章节为基础知识补遗，简明易懂，因此《钥匙书》的内容从《导引》的第二章开始。



## 3.项目更新计划

项目组会优先完成「证明补充」、「案例补充」和「概念补充」的内容。「参考文献讲解」则在前三项工作完成后统一进行。更新计划如下：

​	2020/06/10：第2章、第3章

​	2020/07/10：第4章、第5章

​	2020/08/10：第6章、第7章

​	2020/09/10：第8章、总结



## 4.项目成员

王茂霖：第2章、第3章内容的编辑			

李一飞：第2章、第3章内容的编辑

杨昱文：部分内容的编辑

[@Sm1les](https://github.com/Sm1les)：全球后援团团长

詹	好：项目规划与统筹；第2章、第3章内容的编辑



[1]:关于学习理论的作用，可参阅《机器学习理论导引》1.5节内容。

## 关注我们

<div align=center>
>>>>>>> 321475f89305b0e3e2c4a4f9bdbbab899952cda1
<img src="https://raw.githubusercontent.com/datawhalechina/pumpkin-book/master/res/qrcode.jpeg" width = "250" height = "270" alt="Datawhale——一个专注于AI领域的开源组织">
</div>

## LICENSE
<<<<<<< HEAD

=======
>>>>>>> 321475f89305b0e3e2c4a4f9bdbbab899952cda1
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议</a>进行许可。