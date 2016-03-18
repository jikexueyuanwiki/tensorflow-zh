# 综述 Overview

## Variables: 创建，初始化，保存，和恢复

TensorFlow Variables 是内存中的容纳 tensor 的缓存。这一小节介绍了用它们在模型训练时(during training)创建、保存和更新模型参数(model parameters) 的方法。

[参看教程](../how_tos/variables.md)

## TensorFlow 机制 101 

用 MNIST 手写数字识别作为一个小例子，一步一步的将使用 TensorFlow 基础架构(infrastructure)训练大规模模型的细节做详细介绍。

[参看教程](../tutorials/mnist_tf.md)

## TensorBoard: 学习过程的可视化 

对模型进行训练和评估时，TensorBoard 是一个很有用的可视化工具。此教程解释了创建和运行 TensorBoard 的方法，和使用摘要操作(Summary ops)的方法，通过添加摘要操作(Summary ops)，可以自动把数据传输到 TensorBoard 所使用的事件文件。

[参看教程](../how_tos/summaries_and_tensorboard.md)

## TensorBoard: 图的可视化 

此教程介绍了在 TensorBoard 中使用可视化工具的方法，它可以帮助你理解张量流图的过程并 debug。

[参看教程](../how_tos/graph_viz.md)

## 数据读入 

此教程介绍了把数据传入 TensorSlow 程序的三种主要的方法： Feeding, Reading 和 Preloading.

[参看教程](../how_tos/reading_data.md)

## 线程和队列 

此教程介绍 TensorFlow 中为了更容易进行异步和并发训练的各种不同结构(constructs)。

[参看教程](../how_tos/threading_and_queues.md)

## 添加新的 Op 

TensorFlow 已经提供一整套节点操作(）operation)，你可以在你的 graph 中随意使用它们，不过这里有关于添加自定义操作(custom op)的细节。

[参看教程](../how_tos/adding_an_op.md)。

## 自定义数据的 Readers 

如果你有相当大量的自定义数据集合，可能你想要对 TensorFlow 的 Data Readers 进行扩展，使它能直接以数据自身的格式将其读入。

[参看教程](../how_tos/new_data_formats.md)。

## 使用 GPUs 

此教程描述了用多个 GPU 构建和运行模型的方法。

[参看教程](../how_tos/using_gpu.md)

## 共享变量 Sharing Variables

当在多 GPU 上部署大型的模型，或展开复杂的 LSTMs 或 RNNs 时，在模型构建代码的不同位置对许多相同的变量（Variable）进行读写常常是必须的。设计变量作用域（Variable Scope）机制的目的就是为了帮助上述任务的实现。

[参看教程](../how_tos/variable_scope/index.md)。

原文： [How-to](http://tensorflow.org/how_tos/index.html) 

翻译：[Terence Cooper](https://github.com/TerenceCooper) 

校对：[lonlonago](https://github.com/lonlonago)
<div class='sections-order' style="display: none;">
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
</div>

