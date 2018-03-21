# TensorFlow 官方文档中文版

![](SOURCE/images/tensorflow_logo.png)

### 你正在翻译的项目可能会比 Android 系统更加深远地影响着世界！

## 缘起 

2015年11月9日，Google 官方在其博客上称，Google Research 宣布推出第二代机器学习系统 TensorFlow，针对先前的 DistBelief 的短板有了各方面的加强，更重要的是，它是开源的，任何人都可以用。

机器学习作为人工智能的一种类型，可以让软件根据大量的数据来对未来的情况进行阐述或预判。如今，领先的科技巨头无不在机器学习下予以极大投入。Facebook、苹果、微软，甚至国内的百度。Google 自然也在其中。「TensorFlow」是 Google 多年以来内部的机器学习系统。如今，Google 正在将此系统成为开源系统，并将此系统的参数公布给业界工程师、学者和拥有大量编程能力的技术人员，这意味着什么呢？

打个不太恰当的比喻，如今 Google 对待 TensorFlow 系统，有点类似于该公司对待旗下移动操作系统 Android。如果更多的数据科学家开始使用 Google 的系统来从事机器学习方面的研究，那么这将有利于 Google 对日益发展的机器学习行业拥有更多的主导权。

为了让国内的技术人员在最短的时间内迅速掌握这一世界领先的 AI 系统，极客学院 Wiki 团队发起对 TensorFlow 官方文档的中文协同翻译。

欢迎各路人工智能及机器学习领域的专家和爱好者参与这一翻译项目，我们会为每位翻译和校对人员署名。

## 一起来参与

如果想做出贡献(翻译或者校对)的话，请加QQ群：248320884，谢谢！

PS: 想探讨TensorFlow技术的可以加"TensorFlow技术交流群"：495115006

## 内容来源

英文官方网站：     
<http://tensorflow.org/>

官方GitHub仓库：   
<https://github.com/tensorflow/tensorflow>

中文版 GitHub 仓库：  
<https://github.com/jikexueyuanwiki/tensorflow-zh>

## 关于TensorFlow的一些报道   

[野心：像开放安卓一样，这一次，谷歌决定开放它的机器学习系统——TensorFlow](http://www.huxiu.com/article/130763/1.html?f=wangzhan)   

[最强大机器学习平台开源 谷歌准备主宰人工智能？](http://m.wallstreetcn.com/node/226012)

## 参与步骤

* fork主仓库（<https://github.com/jikexueyuanwiki/tensorflow-zh>）
* 按照章节认领翻译(每次申请一个章节)或者校对(可申请多个章节)在下面这个`README.md`里找还没有被人申请的章节，写上（@你的github号），给主仓库的`master`分支提pull request；
* 提的 pull request 被确认，合并到主仓库后，代表你申请的章节*认领*完成，开始翻译或校对；
* 翻译或校对的文件为README.md或者TOC.md中对应的md文件，请不要翻译/校对单独文件夹中的index.md
* 翻译过程请参照 *翻译协作规范* (见下一节)，完成翻译后提交 pull request 给主仓库的`master`分支；
* 完成校对后同样提交 pull request 给主仓库的`master`分支；
* 全部翻译/校对完成后，我们会生成PDF/ePub文档，放在极客学院Wiki平台发布，并为所有参与者署名！

## 翻译协作规范   

为了让大家协作顺畅，需要每一个人遵循如下协作规范~

- 如果对Markdown和GitHub不了解，请先阅读[如何使用Markdown](markdown.md)以及[如何使用GitHub](learn-github.md)
- 使用Markdown进行翻译，文件名必须使用英文
- 翻译后的文档请放到SOURCE文件夹下的对应章节中，然后pull request即可
- 如遇到文中的图片，请统一放在SOURCE/images目录下
- 原文中的HTML标签及代码请不要修改、翻译
- 有其他任何问题都欢迎发issue，我们看到了会尽快回复
- 翻译人员需将对应的原文地址和翻译人姓名添加到译文末尾，审校人员需要将自己的名字添加到译文末尾，具体格式请参见样例：   

> 原文：[Color Palettes](http://www.google.com/design/spec/resources/color-palettes.html)  翻译：[iceskysl](https://github.com/iceskysl)  校对：[PoppinLp](https://github.com/poppinlp)   

## 校对规范

- 认领校对时请提供机器学习 or AI方面的专业背景说明，保证校对质量
- 文章通顺，适合人类阅读与理解，别让人以为是机翻
- 确保图片都能正常显示，且其相对地址都是SOURCE/images，图片存放正确
- 专有名词符合术语表中的翻译要求，拿不准的新词汇可以使用中文翻译后加括号内英文的形式
- 校对人员需有一定专业背景，保证译文无专业知识方面错误
- 请查看翻译人员是否将原文链接和翻译链接放到译文最下方，审校人员需要将自己的名字添加到译文末尾，具体格式请参见样例：   

> 原文：[Color Palettes](http://www.google.com/design/spec/resources/color-palettes.html)  翻译：[iceskysl](https://github.com/iceskysl)  校对：[PoppinLp](https://github.com/poppinlp)   

- 有任何问题请提Issues或到协同翻译群讨论，校对后提PR等待Merge，管理员通过后会在目录后面打√标识完成

## 参与者（按认领章节排序）

### 翻译 & 校对

- 起步
  - [简介](get_started/introduction.md) 翻译：（[@PFZheng](https://github.com/PFZheng)）√ 校对：（[@yangtze](https://github.com/sstruct)）√
  - [下载及安装](get_started/os_setup.md) 翻译：（[@PFZheng](https://github.com/PFZheng)）√ 校对： （[@yangtze](https://github.com/sstruct)）√
  - [基本用法](get_started/basic_usage.md) 翻译：（[@PFZheng](https://github.com/PFZheng)）√ 校对：（[@yangtze](https://github.com/sstruct)）√
- 教程
  - [综述](tutorials/overview.md) 翻译：（[@PFZheng](https://github.com/PFZheng)）√ 校对： ([@ericxk](https://github.com/ericxk)) √
  - [MNIST机器学习入门](tutorials/mnist_beginners.md) 翻译：([@Tony Jin](https://github.com/linbojin))√ 校对： ([@ericxk](https://github.com/ericxk))
  - [深入MNIST](tutorials/mnist_pros.md) 翻译：([@chenweican](https://github.com/chenweican))√  校对： ([@HongyangWang](https://github.com/WangHong-yang)) √
  - [TensorFlow运作方式入门](tutorials/mnist_tf.md) 翻译：([@bingjin](https://github.com/bingjin))√  校对： ([@LichAmnesia](https://github.com/LichAmnesia)) √
  - [卷积神经网络](tutorials/deep_cnn.md) 翻译： ([@oskycar](https://github.com/oskycar))√  校对： ([@zhyhooo](https://github.com/zhyhooo))
  - [Vector Representations of Words](tutorials/word2vec.md)翻译： ([@btpeter](https://github.com/btpeter)) √ 校对： ([@waiwaizheng](https://github.com/waiwaizheng))
  - [递归神经网络](tutorials/recurrent.md) 翻译：([@Warln](https://github.com/Warln))√  校对： ([@HongyangWang](https://github.com/WangHong-yang))
  - [曼德布洛特(Mandelbrot)集合](tutorials/mandelbrot.md) 翻译：([@ericxk](https://github.com/ericxk))√  校对： ([@tensorfly](https://github.com/tensorfly))√
  - [偏微分方程](tutorials/pdes.md) 翻译：([@wangaicc](https://github.com/wangaicc))√  校对： ([@tensorfly](https://github.com/tensorfly))√
  - [MNIST数据下载](tutorials/mnist_download.md) 翻译： ([@btpeter](https://github.com/btpeter)) √ 校对： ([@waiwaizheng](https://github.com/waiwaizheng))
- 运作方式
  - [总览](how_tos/overview.md) 翻译： ([@Terence Cooper](https://github.com/TerenceCooper))√ 校对：
  （[@lonlonago](https://github.com/lonlonago)) √
  - [变量:创建、初始化、保存和加载](how_tos/variables.md) 翻译： ([@zhyhooo](https://github.com/zhyhooo))√ 校对： ([@jishaoming](https://github.com/jishaoming))
  - [TensorBoard:可视化学习](how_tos/summaries_and_tensorboard.md)翻译：([@thylaco1eo](https://github.com/thylaco1eo))√  校对： ([@lucky521](https://github.com/lucky521)) √
  - [TensorBoard:图表可视化](how_tos/graph_viz.md)  翻译：([@Warln](https://github.com/Warln))√  校对： ([@lucky521](https://github.com/lucky521)) √
  - [读取数据](how_tos/reading_data.md)  翻译： ([@volvet](https://github.com/volvet)) 校对： ([@allensummer](http://github.com/allensummer))
  - [线程和队列](how_tos/threading_and_queues.md) 翻译： ([@zhangkom](https://github.com/zhangkom)) √ 校对：（[@volvet](https://github.com/volvet))√
  - [添加新的Op](how_tos/adding_an_op.md) 翻译：（[@PFZheng](https://github.com/PFZheng)）√校对：（[@ZHNathanielLee](https://github.com/ZHNathanielLee)) √
  - [自定义数据读取](how_tos/new_data_formats.md) 翻译：([@derekshang](https://github.com/derekshang))√ 校对：([@pengfoo](https://github.com/PengFoo))
  - [使用gpu](how_tos/using_gpu.md)翻译：([@lianghyv](https://github.com/lianghyv))√ 校对：([@qiaohaijun](https://github.com/qiaohaijun))
  - [共享变量](how_tos/variable_scope.md) 翻译：([@nb312](https://github.com/nb312))√校对：([@pengfoo](https://github.com/PengFoo))
- 资源
  - [总览](resources/overview.md) 翻译：([@Jim-Zenn](https://github.com/Jim-Zenn))√ 校对：（[@lonlonago](https://github.com/lonlonago)) √
  - [BibTex 引用](resources/bib.md) 翻译：([@Jim-Zenn](https://github.com/Jim-Zenn))√ 校对：([@pengfoo](https://github.com/PengFoo)) 
  - [使用示例](resources/uses.md) 翻译：([@andyiac](https://github.com/andyiac))√ 校对（[@lonlonago](https://github.com/lonlonago)) √
  - [FAQ](resources/faq.md) 翻译：([@Terence Cooper](https://github.com/TerenceCooper))√ 校对：([@pengfoo](https://github.com/PengFoo))
  - [术语表](resources/glossary.md) 翻译： ([@leege100](https://github.com/leege100))√ 校对：
  （[@lonlonago](https://github.com/lonlonago)) √
  - [Tensor的阶、形状和数据类型](resources/dims_types.md) 翻译：([@nb312](https://github.com/nb312))√ 校对：（[@lonlonago](https://github.com/lonlonago)) √
- 其他
  - [常见问题汇总](faq.md)

## 进度记录

- 2015-11-10, 谷歌发布全新人工智能系统TensorFlow并宣布开源, 极客学院Wiki启动协同翻译，创建 GitHub 仓库，制定协同规范 
- 2015-11-18, 所有章节认领完毕，翻译完成18章，校对认领7章，Star数361，fork数100，协同翻译QQ群及技术交流群的TF爱好者将近300人，GitHub搜索TensorFlow排名第二
- 2015-12-10, Star数超过500

## TensorFlow 相关资源

- [Google官方Blog宣布TensorFlow开源](https://googleblog.blogspot.com/2015/11/tensorflow-smarter-machine-learning-for.html)
- [TensorFlow WhitePaper(PDF下载)](http://download.tensorflow.org/paper/whitepaper2015.pdf)
- [Jeff Dean 介绍 TensorFlow（视频）](https://www.youtube.com/watch?v=90-S1M7Ny_o&t=21m2s)
- [TensorFlow 简化版接口 Scikit Flow](https://github.com/google/skflow)
- [TensorFlow 使用样例](https://github.com/aymericdamien/TensorFlow-Examples)
- [TensorFlow 与 mxnet, caffe 对比 @chenrudan](http://chenrudan.github.io/blog/2015/11/18/comparethreeopenlib.html)
- [TensorFlow 与 torch7, caffe, mxnet 在内存使用量以及性能对比 @mli](https://github.com/dmlc/mxnet/blob/master/doc/overview_chn.md)

## 感谢支持

## 离线版本

