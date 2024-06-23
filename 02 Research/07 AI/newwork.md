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



| Method  | Raising | Reading | Writing | mAP0.5 | mAP0.5-0.95 |
| ------- | ------- | ------- | ------- | ------ | ----------- |
| YOLOv8s | 0.82    | 0.649   | 0.699   | 0.722  | 0.524       |
| ours    | 0.824   | 0.657   | 0.694   | 0.725  | 0.529       |


Ours = C2f_PConv_EMA + BiFPN (ALL)

| models   | P     | R     | mAP0.5 | mAP0.5-0.95 | MB   | Para(M) | Flops(G) |
| -------- | ----- | ----- | ------ | ----------- | ---- | ------- | -------- |
| baseline | 0.679 | 0.688 | 0.722  | 0.524       | 22.5 | 11      | 28.4     |
| Ours     | 0.694 | 0.677 | 0.725  | 0.52        |      |         |          |
