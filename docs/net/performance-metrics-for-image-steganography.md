# 图像隐写术的性能指标

> 原文:[https://www . geesforgeks . org/performance-metrics-for-image-steganography/](https://www.geeksforgeeks.org/performance-metrics-for-image-steganography/)

**概述:**
多种方法被用于评估图像隐写术的质量。这些方法中的每一种都评估隐写术后获得的结果的不同方面。一些众所周知的方法是均方误差(MSE)、峰值信噪比(PSNR)、结构化相似性指数度量(SSIM)、有效载荷容量。

**有效载荷能力:**
有效载荷能力是指封面图像中信息量的度量。这一措施在隐写术系统中很重要，因为通信开销取决于最大有效载荷容量。它以每像素位数(BPP)衡量。

```
BPP = NUMBER OF SECRET BITS EMBEDDED/ TOTAL NUMBER OF PIXELS
```

**均方误差(MSE):**
均方误差是原始图像和隐写图像之间的逐像素差的平方的平均值。它为我们提供了由于数据嵌入过程而在封面图像中产生的误差的度量。

```
MSE=(mxn)-1∑mi=1 ∑ni=1I[I(i,j)-k(I,j)]2
```

**描述–**
较低的均方误差值表示嵌入质量良好。

```
m,n = Dimensions of the image
I   = Original Image
K   = stego-image
```

**峰值信噪比(PSNR)** :
PSNR 是另一种流行的方法来测量封面图像因嵌入而失真的程度。它是信号最大可能值和失真噪声功率之间的比值。它以分贝为单位。PSNR 值越高，表示嵌入质量越好。

```
PSNR = 10xlog(MAX2/MSE)
```

**描述–**

```
MAX = 255 for a 8-bit grayscale image
```

**结构化相似性指数测量(SSIM)** :
SSIM 是检查封面图像和隐写图像之间相似性的比较度量。它测量两个图像之间的感知差异。

```
SSIM=(2μxμy + c1)(2σxy +c2)/((μx)2+(μy)2 +c1)((σx)2 +(σy)2 + c2)
```

**描述–**

```
c1 = (k1l)2
c2 = (k2l)2

μx  and μy are the mean intensity values of images x and y. 

(σx)2 is the variance of x, 
(σy)2  is the variance of y 
(σxy)2 is the covariance of x and y. 

c₁ and c₂ are the two stabilizing parameters, 
L is the dynamic range of pixel values (2#bits per pixel - 1)  
the contents k1=0.01 and k2=0.03.
SSIM value close to 1 indicates good quality.
```