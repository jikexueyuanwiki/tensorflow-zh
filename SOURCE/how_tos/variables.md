# 变量:创建、初始化、保存和加载#

当训练模型时，用[变量](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/state_ops.md)来存储和更新参数。变量包含张量 (Tensor)存放于内存的缓存区。建模时它们需要被明确地初始化，模型训练后它们必须被存储到磁盘。这些变量的值可在之后模型训练和分析是被加载。

本文档描述以下两个TensorFlow类。点击以下链接可查看完整的API文档：

- [`tf.Variable`](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/state_ops.md#Variable) 类
- [`tf.train.Saver`](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/state_ops.md#Saver) 类

## 创建

当创建一个[变量](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/state_ops.md)时，你将一个`张量`作为初始值传入构造函数`Variable()`。TensorFlow提供了一系列操作符来初始化张量，初始值是[常量或是随机值](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/constant_op.md)。
 
注意，所有这些操作符都需要你指定张量的shape。那个形状自动成为变量的shape。变量的shape通常是固定的，但TensorFlow提供了高级的机制来重新调整其行列数。

```python
# Create two variables.
weights = tf.Variable(tf.random_normal([784, 200], stddev=0.35),
                      name="weights")
biases = tf.Variable(tf.zeros([200]), name="biases")
```

调用`tf.Variable()`添加一些操作(Op, operation)到graph：

- 一个`Variable`操作存放变量的值。
- 一个初始化op将变量设置为初始值。这事实上是一个`tf.assign`操作.
- 初始值的操作，例如示例中对`biases`变量的`zeros`操作也被加入了graph。

`tf.Variable`的返回值是Python的`tf.Variable`类的一个实例。

## 初始化

变量的初始化必须在模型的其它操作运行之前先明确地完成。最简单的方法就是添加一个给所有变量初始化的操作，并在使用模型之前首先运行那个操作。

你或者可以从检查点文件中重新获取变量值，详见下文。

使用`tf.initialize_all_variables()`添加一个操作对变量做初始化。记得在完全构建好模型并加载之后再运行那个操作。


```python
# Create two variables.
weights = tf.Variable(tf.random_normal([784, 200], stddev=0.35),
                      name="weights")
biases = tf.Variable(tf.zeros([200]), name="biases")
...
# Add an op to initialize the variables.
init_op = tf.initialize_all_variables()

# Later, when launching the model
with tf.Session() as sess:
  # Run the init operation.
  sess.run(init_op)
  ...
  # Use the model
  ...
```    

### 由另一个变量初始化

你有时候会需要用另一个变量的初始化值给当前变量初始化。由于`tf.initialize_all_variables()`是并行地初始化所有变量，所以在有这种需求的情况下需要小心。

用其它变量的值初始化一个新的变量时，使用其它变量的`initialized_value()`属性。你可以直接把已初始化的值作为新变量的初始值，或者把它当做tensor计算得到一个值赋予新变量。

```python
# Create a variable with a random value.
weights = tf.Variable(tf.random_normal([784, 200], stddev=0.35),
                      name="weights")
# Create another variable with the same value as 'weights'.
w2 = tf.Variable(weights.initialized_value(), name="w2")
# Create another variable with twice the value of 'weights'
w_twice = tf.Variable(weights.initialized_value() * 0.2, name="w_twice")
```

### 自定义初始化

`tf.initialize_all_variables()`函数便捷地添加一个op来初始化模型的所有变量。你也可以给它传入一组变量进行初始化。详情请见[Variables Documentation](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/state_ops.md)，包括检查变量是否被初始化。

## 保存和加载

最简单的保存和恢复模型的方法是使用`tf.train.Saver`对象。构造器给graph的所有变量，或是定义在列表里的变量，添加`save`和`restore`ops。saver对象提供了方法来运行这些ops，定义检查点文件的读写路径。

### 检查点文件

变量存储在二进制文件里，主要包含从变量名到tensor值的映射关系。

当你创建一个`Saver`对象时，你可以选择性地为检查点文件中的变量挑选变量名。默认情况下，将每个变量[`Variable.name`](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/state_ops.md#Variable.name)属性的值。

### 保存变量

用`tf.train.Saver()`创建一个`Saver`来管理模型中的所有变量。

```python
# Create some variables.
v1 = tf.Variable(..., name="v1")
v2 = tf.Variable(..., name="v2")
...
# Add an op to initialize the variables.
init_op = tf.initialize_all_variables()

# Add ops to save and restore all the variables.
saver = tf.train.Saver()

# Later, launch the model, initialize the variables, do some work, save the
# variables to disk.
with tf.Session() as sess:
  sess.run(init_op)
  # Do some work with the model.
  ..
  # Save the variables to disk.
  save_path = saver.save(sess, "/tmp/model.ckpt")
  print "Model saved in file: ", save_path
```
	
### 恢复变量

用同一个`Saver`对象来恢复变量。注意，当你从文件中恢复变量时，不需要事先对它们做初始化。

```python
# Create some variables.
v1 = tf.Variable(..., name="v1")
v2 = tf.Variable(..., name="v2")
...
# Add ops to save and restore all the variables.
saver = tf.train.Saver()

# Later, launch the model, use the saver to restore variables from disk, and
# do some work with the model.
with tf.Session() as sess:
  # Restore variables from disk.
  saver.restore(sess, "/tmp/model.ckpt")
  print "Model restored."
  # Do some work with the model
  ...
```

### 选择存储和恢复哪些变量

如果你不给`tf.train.Saver()`传入任何参数，那么saver将处理graph中的所有变量。其中每一个变量都以变量创建时传入的名称被保存。

有时候在检查点文件中明确定义变量的名称很有用。举个例子，你也许已经训练得到了一个模型，其中有个变量命名为`"weights"`，你想把它的值恢复到一个新的变量`"params"`中。

有时候仅保存和恢复模型的一部分变量很有用。再举个例子，你也许训练得到了一个5层神经网络，现在想训练一个6层的新模型，可以将之前5层模型的参数导入到新模型的前5层中。

你可以通过给`tf.train.Saver()`构造函数传入Python字典，很容易地定义需要保持的变量及对应名称：键对应使用的名称，值对应被管理的变量。

注意：

- 如果需要保存和恢复模型变量的不同子集，可以创建任意多个saver对象。同一个变量可被列入多个saver对象中，只有当saver的`restore()`函数被运行时，它的值才会发生改变。
- 如果你仅在session开始时恢复模型变量的一个子集，你需要对剩下的变量执行初始化op。详情请见[`tf.initialize_variables()`](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/api_docs/python/state_ops.md#initialize_variables)。


```python
# Create some variables.
v1 = tf.Variable(..., name="v1")
v2 = tf.Variable(..., name="v2")
...
# Add ops to save and restore only 'v2' using the name "my_v2"
saver = tf.train.Saver({"my_v2": v2})
# Use the saver object normally after that.
...
```

>原文链接: [http://tensorflow.org/how_tos/variables/index.html](http://tensorflow.org/how_tos/variables/index.html) 
>翻译：[赵屹华](https://github.com/zhyhooo) 校对：[Wiki](https://github.com/jikexueyuanwiki)