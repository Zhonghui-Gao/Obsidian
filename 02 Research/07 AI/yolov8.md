MHSA [yolov8添加注意力机制-MHSA_mhsa代码-CSDN博客](https://blog.csdn.net/ROCKY__________/article/details/131804291)

EMA [YOLOv8改进:添加EMA注意力机制_efficient multi-scale attention module with cross--CSDN博客](https://blog.csdn.net/ShawN1022/article/details/132854884)

batchsize= 16
yolov8-pbi.yaml
dataset: SCB-dataset
C2f_PConv BiFPN + WIOU
![[Pasted image 20240521205040.png]]


yolov8n 200 epoch
![[Pasted image 20240522080148.png]]

229 n.pt
![[Pasted image 20240522113203.png]]

yolov8-pbi.yaml  s.pt 424
![[Pasted image 20240523100337.png]]

C2_PCov + BIFPN + BiLevelRoutingAttention + WIou
![[Pasted image 20240524081633.png]]

shapeIou：[损失函数篇 | YOLOv8 引入 Shape-IoU 考虑边框形状与尺度的度量 (ppmy.cn)](https://www.ppmy.cn/news/1294985.html?action=onClick)

C2_PConv + BIFPN + RRA + Shape-IoU 320epochs
![[Pasted image 20240526084510.png]]


batchsize = 8
C2_PConv + BIFPN + WIOU
![[Pasted image 20240526090053.png]]
![[Pasted image 20240526151250.png]]

batch 16 
C2_PCov + BIFPN +  Shape-IoU 367epoch
![[Pasted image 20240527083636.png]]
