# 综述 Overview


## Variables: 创建，初始化，保存，恢复 Variables: Creation, Initializing, Saving, and Restoring

TensorFlow Variables 是内存中的容纳 tensor 的缓存。了解用它们在训练时(during training)保存和更新模型参数(model parameters) 的方法，[参看教程](../how_tos/variables/index.md)。
TensorFlow Variables are in-memory buffers containing tensors.  Learn how to
use them to hold and update model parameters during training.

[View Tutorial](../how_tos/variables/index.md)


## TensorFlow 机制 101 TensorFlow Mechanics 101

用 MNIST 手写数字识别作为一个小例子，一步一步的将使用 TensorFlow 基础架构(infrastructure)训练大规模模型的细节做详细介绍介绍，[参看教程](../tutorials/mnist/tf/index.md)。
A step-by-step walk through of the details of using TensorFlow infrastructure
to train models at scale, using MNIST handwritten digit recognition as a toy
example.

[View Tutorial](../tutorials/mnist/tf/index.md)


## TensorBoard: Visualizing Learning

TensorBoard is a useful tool for visualizing the training and evaluation of
your model(s).  This tutorial describes how to build and run TensorBoard as well
as how to add Summary ops to automatically output data to the Events files that
TensorBoard uses for display.

[View Tutorial](../how_tos/summaries_and_tensorboard/index.md)


## TensorBoard: Graph Visualization

This tutorial describes how to use the graph visualizer in TensorBoard to help
you understand the dataflow graph and debug it.

[View Tutorial](../how_tos/graph_viz/index.md)


## Reading Data

This tutorial describes the three main methods of getting data into your
TensorFlow program: Feeding, Reading and Preloading.

[View Tutorial](../how_tos/reading_data/index.md)


## Threading and Queues

This tutorial describes the various constructs implemented by TensorFlow
to facilitate asynchronous and concurrent training.

[View Tutorial](../how_tos/threading_and_queues/index.md)


## 添加新的 Op Adding a New Op

TensorFlow 已经提供一整套节点操作(operation)，你可以在你的 graph 中随意使用它们，不过这里有关于添加自定义操作(custom op)的细节，[参看教程](../how_tos/adding_an_op/index.md)。
TensorFlow already has a large suite of node operations from which you can
compose in your graph, but here are the details of how to add you own custom Op.
[View Tutorial](../how_tos/adding_an_op/index.md)


## 自定义数据的 Reader Custom Data Readers

如果你有相当大量的自定义数据集合，可能你想要对 TensorFlow 进行扩展，使它能直接以数据自身的格式将其读入，[参看教程](../how_tos/new_data_formats/index.md)。
If you have a sizable custom data set, you may want to consider extending
TensorFlow to read your data directly in it's native format.  Here's how.

[View Tutorial](../how_tos/new_data_formats/index.md)


## 使用 GPU Using GPUs

此教程描述了 用 GPU 构建和运行模型的方法。
This tutorial describes how to construct and execute models on GPU(s).

[View Tutorial](../how_tos/using_gpu/index.md)


## Sharing Variables

When deploying large models on multiple GPUs, or when unrolling complex LSTMs
or RNNs, it is often necessary to access the same Variable objects from
different locations in the model construction code.

The "Variable Scope" mechanism is designed to facilitate that.

[View Tutorial](../how_tos/variable_scope/index.md)

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

