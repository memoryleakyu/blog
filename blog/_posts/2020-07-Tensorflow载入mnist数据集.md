# Tensorflow 载入mnist数据集

最近打算认真学习一下机器学习相关的项目，最好的教程当然是官方文档，所以直接从[官方教程](https://www.tensorflow.org/tutorials/quickstart/beginner)入手。

官网教程里载入数据集是通过在线下载的方式，在更换代理ping通链接但下载仍然失败后，决定更换到本地数据集。于是查了`tf.keras.datasets.mnist.load_data`的API文档，官方给出的方法是 
```python
tf.keras.datasets.mnist.load_data(
    path='mnist.npz'
)
```
把[数据集](https://storage.googleapis.com/tensorflow/tf-keras-datasets/mnist.npz)下载到python文件同一级后，调用仍然失败，因为`path=`这个参数实际是以`~/.keras/datasets/`为根目录的，把数据集`minist.npz`移动到该目录下后，成功本地载入。