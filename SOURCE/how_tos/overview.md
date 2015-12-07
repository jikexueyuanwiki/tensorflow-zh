# 综述


## 变量: 创建，初始化，保存，和恢复

TensorFlow变量是容纳Tensor的内存缓存。学习如何使用它们在训练时，保存和更新模型参数

[参看教程](../how_tos/variables/index.md)


## TensorFlow 机制 101

以MNIST手写数字识别为一个小例子，介绍如何一步步地使用TensorFlow作为基础架构来训练大规模模型

[参看教程](../tutorials/mnist/tf/index.md)


## TensorBoard: 学习过程的可视化

对于可视化训练和评估模型的过程，TensorBoard是一个很有用的工具。此教程展示了如何创建和运行TensorBoard，以及通过添加汇总操作符，把数据输出到事件文件，以供TensorBoard用于展示的方法

[参看教程](../how_tos/summaries_and_tensorboard/index.md)


## TensorBoard: 图的可视化

此教程介绍了如何在TensorBoard中使用图可视化工具的方法，它可以帮助你理解数据流图并进行调试

[参看教程](../how_tos/graph_viz/index.md)


## 数据读入

此教程解释了把数据传入TensorFlow程序的三种主要的方法： 传输，读取和预加载

[参看教程](../how_tos/reading_data/index.md)


## 线程和队列

此教程解释了TensorFlow中，为了方便进行异步和并发训练，而实现的各种不同的结构

[参看教程](../how_tos/threading_and_queues/index.md)


## 添加新的运算符

TensorFlow已经提供一整套的节点运算符，你可以在图中随意使用，这里介绍如何添加自定义运算符的细节

[参看教程](../how_tos/adding_an_op/index.md)


## 自定义数据读取器

如果你有相当大量的自定义数据集合，可能你想要对TensorFlow进行扩展，使它能直接以原生的格式，读入你的数据。请看这里

[参看教程](../how_tos/new_data_formats/index.md)


## 使用 GPUs

此教程描述了如何在GPU上构建和运行模型

[参看教程](../how_tos/using_gpu/index.md)


## 共享变量 Sharing Variables

当在多GPU上部署大型的模型，或展开复杂的LSTMs或RNNs，经常需要在模型构建代码的不同位置，对相同的变量对象进行访问

"变量范围"机制设计的目的就是实现这个

[参看教程](../how_tos/variable_scope/index.md)

原文： [How-to](http://tensorflow.org/how_tos/index.html) 翻译：[Terence Cooper](https://github.com/TerenceCooper) 校对：[Andy Huang](https://github.com/andyyehoo)
<div class='sections-order' style="display: none;">
<!--
<!-- variables/index.md -->
<!-- ../tutorials/mnist/tf/index.md -->
<!-- summaries_and_tensorboard/index.md -->
<!-- graph_viz/index.md -->
<!-- reading_data/index.md -->
<!-- threading_and_queues/index.md -->
<!-- adding_an_op/index.md -->
<!-- new_data_formats/index.md -->
<!-- using_gpu/index.md -->
<!-- variable_scope/index.md -->
-->
</div>
