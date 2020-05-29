# CovidFaceMaskDetector

参考来源：https://github.com/JadHADDAD92/covid-mask-detector


## 如何在jupyter notebook上显示webcam

1. 本地jupyter notebook显示webcam的方法：
https://towardsdatascience.com/video-streaming-in-the-jupyter-notebook-635bc5809e85

注意：这个方式是需要jupyter notebook是运行在本地主机上的才可以

2. Google Colab(或者其他云端主机)显示webcam的方法：
https://colab.research.google.com/drive/1VXSGL_Cpxo2l5vxhxMdrWEtVs-zC0078

Google的Colab不能使用cv2.VideoCapture的原因在于Colab是运行在云端的，所以当调用cv2.VideoCapture函数时是获取云端服务器主机的摄像头，而不是本地本地主机的摄像头，所以需要通过其他方式来获取本地的摄像头信息。如果使用了自己的云端主机，同样要使用这个方法。

Colab的代码snippet也提供给了本地摄像头访问代码，可以实现本地摄像头的拍照。上面这个链接的代码可以进行实时处理，但是处理的帧率较低。

 - 2020.05.29调试记录
 1. 加入了本地摄像头的实时处理。（帧率较低）
 2. 根据参考代码的实现在Colab上训练时会导致Colab卡死，吃掉了本地主机的所有内存（很奇怪，不是在云端训练的吗？）
 3. 加载参考来源训练好的模型，测试无法区分是否佩戴口罩，结果都是有佩戴口罩（很奇怪）
