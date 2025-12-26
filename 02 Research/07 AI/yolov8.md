![[cropped_cropped_yolov8net]]


MHSA [yolov8添加注意力机制-MHSA_mhsa代码-CSDN博客](https://blog.csdn.net/ROCKY__________/article/details/131804291)

EMA [YOLOv8改进:添加EMA注意力机制_efficient multi-scale attention module with cross--CSDN博客](https://blog.csdn.net/ShawN1022/article/details/132854884)

batchsize= 16
yolov8-pbi.yaml
dataset: SCB-dataset
C2f_PConv BiFPN + WIOU
![[Pasted image 20240521205040.png]]


yolov8s 200 epoch
![[Pasted image 20240522080148.png]]

229 n.pt
![[Pasted image 20240522113203.png]]

yolov8-pbi.yaml  s.pt 424
![[Pasted image 20240523100337.png]]

C2_PCov + BIFPN + BiLevelRoutingAttention + WIou 
![[Pasted image 20240524081633.png]]

shapeIou：[损失函数篇 | YOLOv8 引入 Shape-IoU 考虑边框形状与尺度的度量 (ppmy.cn)](https://www.ppmy.cn/news/1294985.html?action=onClick)

C2_PConv + BIFPN + BRA + Shape-IoU 320epochs
![[Pasted image 20240526084510.png]]


batchsize = 8
C2_PConv + BIFPN + WIOU
![[Pasted image 20240526090053.png]]
![[Pasted image 20240526151250.png]]


batch 16 
C2_PCov + BIFPN +  Shape-IoU 367epoch
![[Pasted image 20240527083636.png]]


yolov8s 基础上 C2f all + BIFPN +  Shape-IoU + BRA
![[Pasted image 20240602185234.png]]

C2_PConv(backbone) + BIFPN + BRA + Shape-IoU 320epochs
![[Pasted image 20240526084510.png]]


C2f_PConv_EMA + BiFPN + Shape-IoU
![[Pasted image 20240617095123.png]]





yolov8n 300epoch
![[Pasted image 20240530204440.png]]


YOLOv8s C2_PConv(All) + BIFPN +  Shape-IoU 
![[1718415831809.png]]


C2f_PConv_EMA(backbone) + BiFPN + CIoU
![[Pasted image 20240617095123.png]]


C2f_PConv_EMA(All) + BiFPN + Shape-IoU  0.937
![[Pasted image 20240618095356.png]]

C2f_PConv_EMA(P) + BiFPN + Shape-IoU


yolov8n   8.1 GFLOPs
![[Pasted image 20240615141401.png]]


s 28.4GFLOPs
![[Pasted image 20240615174359.png]]


m 78.7 GFLOPs
![[Pasted image 20240616205459.png]]

l

我们在linux平台下，通过RKNN-Toolkit2在训练好的pt网络模型进行onnx和rknn的模型转换，模型评估，然后通过RKNN-Toolkit-lite进行板端部署运行，在RK3588s平台下，进行以下几个操作：
模型初始化：加载RKNN模型到RKNPU平台，准备进行前处理。
模型前处理：加载待推理数据到RKNPU平台，准备进行推理。
模型推理：执行推理操作，将输入数据传递给模型并获取推理结果。
模型后处理：取出推理结果进行后处理，后处理结果传给应用端。
模型释放：在完成推理流程后，释放模型资源，以便其他任务使用RKNN模型。
我们在默认单个NPU，以及默认的频率下（定频频率直接影响运行速率，频率越高性能相对越好。），模型运行的FPS大概在30左右，以及满足日常需求。后续我们将继续优化模型量化和剪枝，同时优化算法并根据模型逐层性能数据来制定后续不同侧重的优化策略