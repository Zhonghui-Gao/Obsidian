s C2_PConv(All) + BIFPN +  Shape-IoU 
![[1718415831809.png]]


C2f_PConv_EMA + BiFPN + CIoU
![[Pasted image 20240617095123.png]]


C2f_PConv_EMA(All) + BiFPN + Shape-IoU  0.937
![[Pasted image 20240618095356.png]]

C2f_PConv_EMA(P) + BiFPN + Shape-IoU





v8n

![[Pasted image 20240618202724.png]]


![[Pasted image 20240620002422.png]]

v8s

![[Pasted image 20240618202801.png]]




C2f_PConv_EMA(Backbone) + BiFPN(C2f) + CIoU 1
![[Pasted image 20240619001431.png]]



C2f_PConv_EMA(All) + BiFPN + Shape-IoU  0.937
![[Pasted image 20240618202652.png]]

C2f_PConv_EMA(All) + BiFPN + CIoU   0.937

![[Pasted image 20240618222943.png]]

C2f_PConv_EMA(All) + PAnet(C2f_PConv_EMA) + CIoU

![[Pasted image 20240619093508.png]]

C2f_PConv_EMA(Backbone) + PAnet(C2f) + CIoU

![[Pasted image 20240619105632.png]]




C2f_PConv_EMA(Backbone) + BiFPN(C2f) + ShapeIoU

![[Pasted image 20240619140509.png]]



C2f_PConv_EMA(Backbone) + BiFPN(C2f) + CIoU 1
![[Pasted image 20240619001431.png]]



C2f_PConv(Backbone) + BiFPN(C2f_PConv_EMA) + Shape-IoU

![[Pasted image 20240619175835.png]]


C2f_PConv(Backbone) + BiFPN(C2f_PConv_EMA) + CIoU


v8m + Shape-IoU
![[Pasted image 20240619155448.png]]


v8m  CIoU

![[Pasted image 20240619222446.png]]


BIFPN 256 
C2f_PConv(Backbone) + BiFPN(C2f_PConv_EMA) + CIoU
![[Pasted image 20240621001055.png]]


C2f_PConv_EMA(ALL) + BiFPN + CIoU       2 
![[Pasted image 20240621085528.png]]

C2f_PConv_EMA(Backbone) + BiFPN(C2f) + CIoU
![[Pasted image 20240621103933.png]]

C2f_PConv_EMA(Backbone) + PAnet(C2f) + CIoU

![[Pasted image 20240619105632.png]]



C2f + BiFPN(C2f_PConv_EMA) + CIoU
![[Pasted image 20240621122243.png]]


yolov5m 48.2G FPS 159.603
![[1719450174370.jpg]]

yolov5s 15.8 7M 14.5 MB
![[Pasted image 20240627143354.png]]


yolov7-tiny 12.3MB 
![[Pasted image 20240628090500.png]]

| Method  | Raising | Reading | Writing | mAP0.5 | mAP0.5-0.95 |
| ------- | ------- | ------- | ------- | ------ | ----------- |
| YOLOv8s | 0.82    | 0.649   | 0.699   | 0.722  | 0.524       |
| ours    | 0.824   | 0.657   | 0.694   | 0.725  | 0.529       |


Ours = C2f_PConv_EMA + BiFPN (ALL)
减少一倍的运算量和模型大小 保持精度不变
Fps
比较结果如表格3所示，其中采用BiFPN情况下优于传统的YOLOv8的PAnet能做到更轻量，特征融合能力更强，在主干网络中采用C2f_PConv_EMA模块在融合部分优于C2f，同时在头部网络中采用BiFPN情况下再结合C2f_PConv_EMA模块，效果是最佳的。

| nums | models                                       | P         | R         | mAP0.5    | mAP0.5-0.95 | MB       | Para(M) | Flops(G) |
| ---- | -------------------------------------------- | --------- | --------- | --------- | ----------- | -------- | ------- | -------- |
|      | baseline C2f + PANet                         | 0.679     | 0.688     | 0.722     | 0.524       | 22.5     | 11      | 28.4     |
| 1    | C2f_PConv_EMA(Backbone)+BiFPN(C2f_PConv_EMA) | **0.694** | 0.677     | **0.725** | 0.529       | **12.0** | **5**   | **18.1** |
| 2    | C2f_PConv_EMA(Backbone)+PANet(C2f)           | 0.672     | 0.682     | 0.715     | 0.**531**   | 19.7     | 9       | 24.6     |
| 3    | C2f_PConv_EMA(Backbone)+BiFPN(C2f)           | 0.666     | 0.694     | 0.719     | 0.53        | 12.4     | 6       | 19.1     |
| 4    | C2f_PConv_EMA(Backbone)+PANet(C2f_PConv_EMA) | 0.671     | **0.701** | 0.72      | 0.527       | 17       | 8       | 22.1     |
| 5    | C2f(Backbone)+BiFPN(C2f_PConv_EMA)           | 0.659     | 0.686     | 0.706     | 0.514       | 14.8     | 7       | 22       |
 

2和3对比
1和4对比 证明BiFPN优于PANet 轻量和特征融合能力更强

| nums | models                             | P     | R     | mAP0.5 | mAP0.5-0.95 | MB   | Para(M) | Flops(G) |
| ---- | ---------------------------------- | ----- | ----- | ------ | ----------- | ---- | ------- | -------- |
| 2    | C2f_PConv_EMA(Backbone)+PANet(C2f) | 0.672 | 0.682 | 0.715  | 0.**531**   | 19.7 | 9       | 24.6     |
| 3    | C2f_PConv_EMA(Backbone)+BiFPN(C2f) | 0.666 | 0.694 | 0.719  | 0.53        | 12.4 | 6       | 19.1     |

| nums | models                                       | P         | R         | mAP0.5    | mAP0.5-0.95 | MB       | Para(M) | Flops(G) |
| ---- | -------------------------------------------- | --------- | --------- | --------- | ----------- | -------- | ------- | -------- |
| 1    | C2f_PConv_EMA(Backbone)+BiFPN(C2f_PConv_EMA) | **0.694** | 0.677     | **0.725** | 0.529       | **12.0** | **5**   | **18.1** |
| 4    | C2f_PConv_EMA(Backbone)+PANet(C2f_PConv_EMA) | 0.671     | **0.701** | 0.72      | 0.527       | 17       | 8       | 22.1     |


1和5 对比
baseline和2对比：证明C2f_PConv_EMA(Backbone)

| nums | models                                       | P         | R     | mAP0.5    | mAP0.5-0.95 | MB       | Para(M) | Flops(G) |
| ---- | -------------------------------------------- | --------- | ----- | --------- | ----------- | -------- | ------- | -------- |
| 1    | C2f_PConv_EMA(Backbone)+BiFPN(C2f_PConv_EMA) | **0.694** | 0.677 | **0.725** | 0.529       | **12.0** | **5**   | **18.1** |
| 5    | C2f(Backbone)+BiFPN(C2f_PConv_EMA)           | 0.659     | 0.686 | 0.706     | 0.514       | 14.8     | 7       | 22       |

| nums | models                             | P     | R     | mAP0.5 | mAP0.5-0.95 | MB   | Para(M) | Flops(G) |
| ---- | ---------------------------------- | ----- | ----- | ------ | ----------- | ---- | ------- | -------- |
|      | baseline                           | 0.679 | 0.688 | 0.722  | 0.524       | 22.5 | 11      | 28.4     |
| 2    | C2f_PConv_EMA(Backbone)+PANet(C2f) | 0.672 | 0.682 | 0.715  | 0.**531**   | 19.7 | 9       | 24.6     |


2和4对比
1和3对比
证明：C2f_PConv_EMA在融合部分优于C2f 同时更轻量

| nums | models                                       | P         | R         | mAP0.5    | mAP0.5-0.95 | MB       | Para(M) | Flops(G) |
| ---- | -------------------------------------------- | --------- | --------- | --------- | ----------- | -------- | ------- | -------- |
| 2    | C2f_PConv_EMA(Backbone)+PANet(C2f)           | 0.672     | 0.682     | 0.715     | 0.**531**   | 19.7     | 9       | 24.6     |
| 4    | C2f_PConv_EMA(Backbone)+PANet(C2f_PConv_EMA) | 0.671     | **0.701** | 0.72      | 0.527       | 17       | 8       | 22.1     |

| nums | models                                       | P         | R     | mAP0.5    | mAP0.5-0.95 | MB       | Para(M) | Flops(G) |
| ---- | -------------------------------------------- | --------- | ----- | --------- | ----------- | -------- | ------- | -------- |
| 1    | C2f_PConv_EMA(Backbone)+BiFPN(C2f_PConv_EMA) | **0.694** | 0.677 | **0.725** | 0.529       | **12.0** | **5**   | **18.1** |
| 3    | C2f_PConv_EMA(Backbone)+BiFPN(C2f)           | 0.666     | 0.694 | 0.719     | 0.53        | 12.4     | 6       | 19.1     |


1和2对比证明 BiFPN + C2f_PConv_EMA 效果最好

| 1   | C2f_PConv_EMA(Backbone)+BiFPN(C2f_PConv_EMA) | **0.694** | 0.677 | **0.725** | 0.529     | **12.0** | **5** | **18.1** |
| --- | -------------------------------------------- | --------- | ----- | --------- | --------- | -------- | ----- | -------- |
| 2   | C2f_PConv_EMA(Backbone)+PANet(C2f)           | 0.672     | 0.682 | 0.715     | 0.**531** | 19.7     | 9     | 24.6     |

网络设置：



|                      | P         | R     | mAP       | GFLOPs | MB       | Para(M) |
| -------------------- | --------- | ----- | --------- | ------ | -------- | ------- |
| yolov5m              | 0.690     | 0.695 | 0.721     | 48.2   | 42.2     | 20.8    |
| yolov5s              | 0.675     | 0.695 | 0.703     | 16     | 14.5     | 7       |
| yolov7-tiny          | 0.682     | 0.685 | 0.705     | 13.2   | 12.3     | 6.0     |
| yolov8s              | 0.679     | 0.688 | 0.722     | 28.4   | 22.5     | 11.1    |
| ours                 | **0.694** | 0.677 | **0.725** | 18.1   | **12.0** | 5.8     |
| yolov10s             | 0.667     | 0.698 | 0.723     | 21.6   | 16.6     | 7.2     |
| yolov11s             | 0.709     | 0.697 | **0.753** | 21.5   | 19.2     | 9.4     |
| yolov7s+BRA+W1/W2/W3 |           |       |           |        |          |         |
| yolov10m             | 0.677     | 0.698 | 0.738     | 59.1   |          | 16.4    |
| yolov8+mobileNetv3   |           |       |           |        |          |         |
| yolov8+ghostNetv3    |           |       |           |        |          |         |
|                      |           |       |           |        |          |         |
|                      |           |       |           |        |          |         |


yolov10s![[Pasted image 20241114211608.png]]

yolov11s
![[Pasted image 20241114002337.png]]

yolov8-EMA-backbone
![[Pasted image 20250507180948.png]]
batchsize 32
![[Pasted image 20250508151855.png]]


yolov8-EMA-head
![[Pasted image 20250507200551.png]]

![[Pasted image 20250508152112.png]]

cf_PConv-backbone
![[Pasted image 20250507224901.png]]

![[Pasted image 20250508152710.png]]

C2f_PConv-head
![[Pasted image 20250508000734.png]]

![[Pasted image 20250508161452.png]]

数据集 
VOC2007
train5
![[Pasted image 20250508183239.png]]



mynet
![[Pasted image 20250508081647.png]]

![[Pasted image 20250508191010.png]]


batch 1
![[Pasted image 20250508103255.png]]
yolov8s



STB-08
mynet

![[Pasted image 20250508151051.png]]

yolov8s
![[Pasted image 20250508204512.png]]


将基于 YOLOv8 的改进模型与YOLOv5m、YOLOv5s、YOLOv7-tiny,YOLOv10,YOLOv11等主流目标检测网络模型进行对比，试验结果如表4所示。
由表4可知，改进后的模型权重，计算量均小于其他模型，精确度相较于其他模型比较分别提高了0.4%，1.9%，1.2%，1.5%，2.7%，1.7%。在权重大小中，相较于其他模型比较分别减少了71.6%,17%,2.4%,47.7%,27.7%,78.3%,37.5,计算量相较于其他模型分别减少了86.5%，17.1%，3.3%，47.7%, 73.1%, 64.6%, 38.3%。改进后的模型相较于主流的网络来说，模型参数量和计算复杂度上表现更优，适合轻量化场景，为教室部署轻量化网络提供了有效的模型。



由表 5 可知，YOLOv8-PBi 的模型权重均小于其他
模型，精确率、召回率、平均精度均大于其他模型，其
中平均精度分别比 SSD、RCNN、YOLOv5s、YOLOv5m、
YOLOv7-tiny、YOLOv8s 分别高出 21.3、47.8、4.4、1.9、
6.2、1.8 个百分点，同时模型权重相较于 SSD、RCNN、
YOLOv5s、YOLOv5m、YOLOv7-tiny、YOLOv8s，分别
减 小了 86.64%、 88.80%、 15.97%、 71.33%、 1.63%、
46.22%。Two-stage 网络模型 Fast-RCNN 的权重和计算
量较大，且识别精度较低。One-Stage 网络模型 SSD、
YOLOv5s、YOLOv5m、YOLOv7-tiny、YOLOv8s 的权
重和计算量小于 Fast-RCNN，同时检测精度更高。改进
后的 YOLOv8-PBi 相较于其他主流网络，对于板栗果实
目标的检测效果更好。


为了评估为改进YOLOv8而提出的各种模块的有效性，我们将改进后的YOLOv8算法与其不同组成模块，在主干网络和头部网络分别进行组合比较，即YOLOv8+C2f_PConv_EMA(Backbone)+BiFPN(C2f_PConv_EMA)，YOLOv8+C2f_PConv_EMA(Backbone)+PANet(C2f)，YOLOv8+C2f_PConv_EMA(Backbone)+BiFPN(C2f)，
YOLOv8+C2f_PConv_EMA(Backbone)+PANet(C2f_PConv_EMA)，YOLOv8+C2f(Backbone)+BiFPN(C2f_PConv_EMA)
（在这里分别用v1，v2，v3，v4，v5表示），以及原始的YOLOv8s算法下进行比较。
在主干网络中采用C2f\_PConv_EMA和在头部网络采用BiFPN同时采用C2f\_PConv_EMA，用V1表示；
在主干网络中采用C2f\_PConv_EMA和在头部网络采用PANet不采用C2f\_PConv_EMA，用V2表示；
在主干网络中采用C2f\_PConv_EMA和在头部网络采用BiFPN不采用C2f\_PConv_EMA，用V3表示；
在主干网络中采用C2f\_PConv_EMA和在头部网络采用PANet同时采用C2f\_PConv_EMA，用V4表示；
在主干网络中不采用C2f\_PConv_EMA和在头部网络采用BiFPN同时采用C2f\_PConv_EMA，用V5表示；



YOLOv8+C2f\_PConv\_EMA(Backbone)+BiFPN(C2f\_PConv\_EMA),
YOLOv8+C2f\_PConv\_EMA(Backbone)+PANet(C2f),YOLOv8+C2f\_PConv\_EMA(Backbone)+BiFPN(C2f),YOLOv8+C2f\_PConv\_EMA(Backbone)+PANet(C2f\_PConv\_EMA), and YOLOv8+C2f(Backbone)+BiFPN(C2f\_PConv\_EMA) (denoted as v1, v2, v3, v4, and v5, respectively).


即YOLOv8 + MobileViTv3 + Wise-IoU、YOLOv8 + MobileViTv3、YOLOv8 + Wise-IoU以及原始YOLOv8算法进行了比较。表3和表4分别显示了VisDrone2019和DOTA验证集上的消融实验结果。表3显示，改进后的YOLOv8算法在VisDrone2019验证集上的各项指标上均取得了最佳性能，mAP为34.2%，查准率为45.1%，查全率为33.7%。这表明改进的YOLOv8算法可以使用视觉变压器MobileViTv3有效提取更丰富、更强大的特征表示，并使用Wise-IoU损失函数优化边界框回归，从而提高小目标检测精度。同样，表4显示，改进后的YOLOv8算法在DOTA验证集上的所有指标上也优于所有其他三个组成模块，mAP为71.3%，查准率为87.1%，查全率为67.1%。这表明改进的YOLOv8算法能够有效适应遥感图像中小目标的多样性和变异性，具有较高的方向性不变性和多尺度适应性。

batch16
baseline 
![[Pasted image 20250508094548.png]]

V1 
![[Pasted image 20250508094530.png]]

V2
![[1746668818369.png]]
V3
![[1746668890595.png]]
V4
![[1746669089835.png]]
V5
![[Pasted image 20250508095257.png]]


batchsize 1
baseline
![[Pasted image 20250508103453.png]]

V1
![[Pasted image 20250508103647.png]]
V2
![[Pasted image 20250508104042.png]]
V3
![[Pasted image 20250508104141.png]]

V4
![[Pasted image 20250508104346.png]]

V5
![[Pasted image 20250508104537.png]]


batchsize 32
baseline 60
![[Pasted image 20250508122236.png]]


V1 62
![[Pasted image 20250508120616.png]]
V2
![[Pasted image 20250508121104.png]]
V3

![[Pasted image 20250508121215.png]]

V4
![[Pasted image 20250508122431.png]]
V5
![[Pasted image 20250508122335.png]]