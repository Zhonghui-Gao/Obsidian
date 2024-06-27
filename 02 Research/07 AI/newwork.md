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

| Method  | Raising | Reading | Writing | mAP0.5 | mAP0.5-0.95 |
| ------- | ------- | ------- | ------- | ------ | ----------- |
| YOLOv8s | 0.82    | 0.649   | 0.699   | 0.722  | 0.524       |
| ours    | 0.824   | 0.657   | 0.694   | 0.725  | 0.529       |


Ours = C2f_PConv_EMA + BiFPN (ALL)
减少一倍的运算量和模型大小 保持精度不变
Fps

| nums | models                                       | P         | R         | mAP0.5    | mAP0.5-0.95 | MB       | Para(M) | Flops(G) |
| ---- | -------------------------------------------- | --------- | --------- | --------- | ----------- | -------- | ------- | -------- |
|      | baseline                                     | 0.679     | 0.688     | 0.722     | 0.524       | 22.5     | 11      | 28.4     |
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





|             | P         | R     | mAP       | GFLOPs | MB       | Para(M) |
| ----------- | --------- | ----- | --------- | ------ | -------- | ------- |
| yolov5m     | 0.690     | 0.695 | 0.721     | 48.2   | 42.2     | 20.8    |
| yolov5s     | 0.675     | 0.695 | 0.703     | 16     | 14.5     | 7       |
| yolov7-tiny |           |       |           | 13.2   |          | 6.0     |
| yolov8s     | 0.679     | 0.688 | 0.722     | 28.4   | 22.5     | 11.1    |
| ours        | **0.694** | 0.677 | **0.725** | 18.1   | **12.0** | 5.8     |
