
#术语表

###广播系统(Broadcasting operation)
一种用颠簸式广播来兼容它的tensor参数形状的系统。

###Devices
一快可以用来运算并且有自己的地址空间的硬件，比如GPU和CPU。
###eval
返回Tesor值的一个方法，触发任意一个图表计算都需要得出这个值。只能在一个已经开启了会话图表中的Tensor上里调用。
###Feed
TensorFlow中的一个原理：把一个tensor直接连接到任意一个会话中图表的节点。feed不是在构建图表(graph)的时候创建，而是在触发图表的执行操作时去申请。feed临时替代带有tensor值的节点。把feed数据作为run()方法和eval()方法的参数叫做初始化运算。方法运行结束后,feed就会消失，而最初的节点定义会留下。可以通过tf.placeholder()把特定的节点指定为feed节点。点击这里查看更多信息[Basic Usage](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/get_started/basic_usage.md).
###Fetch
TensorFlow中的一个原理：从一个会话图表中取回tensor。取回fetches的申请发生在触发图表执行的操作，而不是发生在建立图表的时候。如果要取回node或多个node的tensor值，可以通过在Session对象上调用run方法并将传递待取回节点(node)的列表作为参数来执行图表(graph)。详见[Basic Usage](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/get_started/basic_usage.md)。
###Graph
把运算描述成一个直接的无环图形（DAG）,图表中的节点（node）代表必须实现的一个操作。图表中的边代表数据或者可控的依赖。GratheDef是一个把系统描述成一个图表的协议(api)，一个GraphDef可以转化成一个更容易操作的图表对象。
###IndexedSlices（索引化的切片）
在Python API中，TensorFlow仅仅在第一维上对tensor有所体现。如果tensor在一个k维空间里，一个IndexedSlices实例在逻辑上代表一个沿着这个tensor第一维的(k-1)维集合。切片的索引被连续储存在一个单独的一维向量中，而相关的切片被连接成一个单独的k维tensor。如果sparsity(稀疏、贫乏)不是受限于一维空间，就用SparseTensor。

###Node
图表中的一个元素。
把怎样调用一个特定操作描述成一个特定的运算图表，包括任何需要用来配置这个操作的参数的值。对于那些多形性的操作，这些参数包括能完全决定这个节点（Node）的签名。详情见graph.proto。
###操作（Op/operation）
在TensorFlow的运行时中:一种类似add或matmul或concat。可以用[how to add an op](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/how_tos/adding_an_op/index.md)这种方法来向运行时添加操作。
在Python的Api中：图表中的一个节点。Ops在这个类[tf.Operation](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/framework.md#Operation)中列举出来了。一个操作(Operation)的type属性代表这个节点（node）的操作，比如add和matmul。
###Run
在运行的图表中执行ops的行为。要求这个图表运行在一个会话中。
在Python的API中：是Session类的一个方法[tf.Session.run](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/client.md#Session)。可以通过tensors去feed或fetch来调用run()操作。
在C++API中：是一个用来开启一个图表并运行操作的类[tensorflow::Session](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassSession.md)
###Shape
Tensor的维度和他们的长度。
在运行的图表中，它表示存在于节点（node）之间Tensor的属性。一些操作强烈要求shape不能在运行时出现输入和输出错误的shape。
在Python的API中，是图表结构API中Tensor的参数。在Tensor的Shape的构建中，只有部分可见，甚至全都不可见。详情见这里[tf.TensroShape](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/framework.md#TensorShape)
在C++中，Shape类用来表现Tensor的Shape[tensorflow::TensorShape](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassTensorShape.md)。
###SparseTensor
在Python API中，TensorFlow对tensor的体现散落在任意位置。SparseTensor仅仅以字典值格式来储存切片(slices)中的非空值。换言之，m个非空值，就包含一个长度为m的值向量和一个由m列索引(indices)组成的矩阵。为了更高的效率，SparseTensor需要将indice（索引）按增量排序存储,比如行主序。如果排列不仅仅沿着第一维度，就用IndexedSlices。
###Tensor
Tensor是一种特定的多维数组。比如，一个用浮点型数据组成的四维数组代表一小批由【batch,高，宽，channel】组成的数组。
在一个运行的图表中，是一种连接在节点（node）之间的数据。
在Python中，Tensor用来表示添加到图表的操作(op)中的输入和输出，这样的类不持有数据，见[tf.Tensor](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/python/framework.md#Tensor)。
在C++中，Tensor用来表示通过[Session::Run()](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassSession.md)方法调用[tensorflow::Tensor](https://github.com/jikexueyuanwiki/tensorflow-zh/blob/master/SOURCE/api_docs/cc/ClassTensor.md)的值，这样的Tensor持有数据。