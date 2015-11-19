
#术语表

###广播操作(Broadcasting operation)
一种用[numpy-style broadcasting](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)来保证tensor参数的形态兼容的操作。

###Devices
一块可以用来运算并且拥有自己的地址空间的硬件，比如GPU和CPU。
###eval
Tensor的一个方法，返回Tensor的值。触发任意一个图表计算都需要计算出这个值。只能在一个会话图表中的Tensor上调用。
###Feed
TensorFlow的一个概念：把一个tensor直接连接到一个会话图表中的任意节点。feed不是在构建图表(graph)的时候创建，而是在触发图表的执行操作时去申请。一个feed临时替代一个带有tensor值的节点。把feed数据作为run()方法和eval()方法的参数来初始化运算。方法运行结束后，feed就会消失，而最初的节点定义仍然还在。可以通过tf.placeholder()把特定的节点指定为feed节点来创建它们。详见[Basic Usage](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/get_started/basic_usage.md).
###Fetch
TensorFlow中的一个概念：从一个会话图表中取回tensor。取回fetches的申请发生在触发执行图表操作的时候，而不是发生在建立图表的时候。如果要取回一个或多个节点（node）的tensor值，可以通过在Session对象上调用run()方法并将待取回节点（node）的列表作为参数来执行图表(graph)。详见[Basic Usage](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/get_started/basic_usage.md)。
###Graph(图表)
把运算描述成一个直接的无环图形（DAG），图表中的节点（node）代表必须要实现的一些操作。图表中的边代表数据或者可控的依赖。GratheDef是系统中描述一个图表的协议(api)，它由一个NodeDefs集合组成。一个GraphDef可以转化成一个更容易操作的图表对象。
###IndexedSlices（索引化切片）
在Python API中，TensorFlow仅仅在第一维上对tensor有所体现。如果一个tensor有k维，那么一个IndexedSlices实例在逻辑上代表一个沿着这个tensor第一维的(k-1)维切片的集合。切片的索引被连续储存在一个单独的一维向量中，而对应的切片则被拼接成一个单独的k维tensor。如果sparsity不是受限于第一维空间，请用SparseTensor。

###Node（节点）
图表中的一个元素。
把启动一个特定操作的方式称为特定运算图表中的一个节点，包括任何用来配置这个操作的属性的值。对于那些多形态的操作，这些属性包括能完全决定这个节点（Node）签名的充分信息。详见graph.proto。
###操作（Op/operation）
在TensorFlow的运行时中，它是一种类似add或matmul或concat的运算。可以用[how to add an op](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/how_tos/adding_an_op/index.md)中的方法来向运行时添加新的操作。

在Python的API中，它是图表中的一个节点。在[tf.Operation](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/framework.md#Operation)类中列举出了这些操作。一个操作(Operation)的type属性决定这个节点（node）的操作类型，比如add和matmul。
###Run
在一个运行的图表中执行某种操作的行为。要求这个图表必须运行在一次会话中。

在Python的API中，它是Session类的一个方法[tf.Session.run](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/client.md#Session)。可以通过tensors来订阅或获取run()操作。

在C++的API中，[tensorflow::Session](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/client.md#Session)的一个方法。
###Session(会话)
一个已经启动的图表(graph)的运行时对象。提供在图表中执行操作的一些方法。

在Python API中，[tf.Session](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/client.md#Session)。

在C++API中，它是一个用来开启一个图表并运行操作的类：[tensorflow::Session](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassSession.md)
###Shape
Tensor的维度和他们的大小。

在一个已经启动的图表中，它表示建立在节点（node）之间的Tensor的属性。一些操作强烈要求shape不能在运行时出现未知的输入和输出错误。

在Python API中，是图表构造API中Tensor的属性。在Tensor的Shape的构建中，要么只有部分已知，要么全部未知。见[tf.TensroShape](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/framework.md#TensorShape)

在C++中，Shape类用来表现Tensor的外形[tensorflow::TensorShape](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassTensorShape.md)。
###SparseTensor
在Python API中，TensorFlow对tensor的表现很散落在任意地方。SparseTensor以字典值格式来储存那些沿着索引的非空值。换言之，m个非空值，就包含一个长度为m的值向量和一个由m列索引(indices)组成的矩阵。为了提升效率，SparseTensor需要将indice（索引）按维度的增加来按序存储，比如行主序。如果稀疏值仅沿着第一维度，就用IndexedSlices。
###Tensor
Tensor是一种特定的多维数组。比如，一个浮点型的四维数组表示一小批由[batch,height，width，channel]组成的图片。

在一个运行的图表(graph)中，它是一种连接在节点（node）之间的数据。
在Python中，Tensor类表示添加到图表的操作中的输入和输出，见[tf.Tensor](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/framework.md#Tensor)，这样的类不持有数据。

在C++中，Tensor是方法[Session::Run()](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassSession.md)的返回值，见[tensorflow::Tensor](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassTensor.md)，这样的Tensor持有数据。

原文：[Glossary](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/g3doc/resources/glossary.md) 翻译：[leege100](https://github.com/leege100)