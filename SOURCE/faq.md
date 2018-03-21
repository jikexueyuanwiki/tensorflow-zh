# 常见问题汇总

## 说明

本章非官方文档翻译，是由众多TensorFlow爱好者将安装和使用TF过程中的问题总结而成的。

## 常见问题及解答

### (示例)官网地址是哪里？

[http://www.tensorflow.org/](http://www.tensorflow.org/)

### 如何安装 pip ？

 * Ubuntu (14.04)

        sudo apt-get update && sudo apt-get install -y python python-dev python-pip

 * CentOS 7

        yum update -y && yum install -y python python-devel epel-release.noarch python-pip

 * MACOS

        sudo easy_install pip

### docker run -it b.gcr.io/tensorflow/tensorflow 失败

该镜像所在仓库被墙，需要梯子。

[这里](http://pan.baidu.com/s/1bnyVrMR)（密码：v9ts）有镜像的导出包。
使用方法

    docker load < sensorflow.tar.gz

### SSLError: SSL_VERIFY_FAILED

在用url通过pip的方式安装的时候，可能会遇到的错误如下：

        SSLError: [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed (_ssl.c:590)

解决办法:先下载wheel到本地，之后本地pip install
