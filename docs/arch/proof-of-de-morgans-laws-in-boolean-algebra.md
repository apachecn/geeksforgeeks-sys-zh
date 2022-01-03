# 布尔代数中德摩根定律的证明

> 原文:[https://www . geeksforgeeks . org/布尔代数中的摩根法则证明/](https://www.geeksforgeeks.org/proof-of-de-morgans-laws-in-boolean-algebra/)

**语句:**
**1。![(x+y)'= x'. y'](img/4dacd0d1d13f6d2d482ade55306ddfd8.png "Rendered by QuickLaTeX.com")** 
**2。![(x.y)'=x'+y'](img/3b59110d43cd0ccc4057b9a083c2fed8.png "Rendered by QuickLaTeX.com")**

**证明:**
这里可以看出，我们需要证明两个命题是相辅相成的。
我们知道![A+A'=1](img/130a9a4877b80d32447c53b870b000b6.png "Rendered by QuickLaTeX.com")和![A.A'=0](img/409a20e4eb97d30a8e0649650fd61161.png "Rendered by QuickLaTeX.com")这是湮灭定律。因此，如果我们证明上述法律陈述的这些条件，那么我们将证明它们是相互补充的。

**对于陈述 1:**
我们需要证明:
![(x+y)+x'.y'=1](img/1f518d70262603ec324c043068b68e1b.png "Rendered by QuickLaTeX.com")和![(x'.y').(x+y)=0](img/018b69a6e12232655a030cbf54eb3d48.png "Rendered by QuickLaTeX.com")

**案例 1。** ![ (x+y)+x'.y'=1 ](img/fcfc1685b26e818a508d1acb6f19bb32.png "Rendered by QuickLaTeX.com")
![LHS: (x+y)+x'.y' =(x+y).(x+x')+x'.y'](img/2d818df206e3a346512da4323966c9a7.png "Rendered by QuickLaTeX.com")
![=x.x+x.y+y.x'+x'.y'=x+x.y+y.x'+x'.y'](img/aee5f2812083744b48acd35eccf50fef.png "Rendered by QuickLaTeX.com"){利用分配属性}
![=x+x.y+x'.(y+y')](img/fa5173d5f74ed5764a894e5dff99108d.png "Rendered by QuickLaTeX.com")
![=x+x.y+x'=x+x'+x.y ](img/71436ab1d928cf0a7227dade4710eeff.png "Rendered by QuickLaTeX.com")
![ =1+x.y=1=RHS](img/08f6066c8a6ebc233b4954d1b7488784.png "Rendered by QuickLaTeX.com")
遂被证明。

**案例二。** ![ (x'.y').(x+y)=0 ](img/21ab69fe25757cdbbade7fcf22e30f0a.png "Rendered by QuickLaTeX.com")
![LHS: (x'.y').(x+y)=x.(x'y')+y.(x'.y')](img/df266eeb2e13cfd4a604e16cc24161e1.png "Rendered by QuickLaTeX.com")
![=x.0+0.x'=0=RHS](img/334d649179b473c170bff86f500647e3.png "Rendered by QuickLaTeX.com")
遂证。

**对于陈述 2:**
我们需要证明:
![x.y+(x'+y')=1](img/d302a1fe8e97561ce0d47e9c3c82dfd0.png "Rendered by QuickLaTeX.com")和![x.y.(x'+y')=0](img/9261776f49c67815eadf0ef65a911355.png "Rendered by QuickLaTeX.com")

**案例 1。** ![x.y+(x'+y')=1](img/d302a1fe8e97561ce0d47e9c3c82dfd0.png "Rendered by QuickLaTeX.com")
![ LHS: x.y+(x'+y')=(x+x'+y').(y+x'+y')](img/163672232c32154e0c4c28d9281de476.png "Rendered by QuickLaTeX.com")
{我们知道 A+BC=(A+B)。(A+C)}
![=(1+y').(1+x')=1=RHS](img/ca40c1b9cc1471d32144bb66b7dcd6a2.png "Rendered by QuickLaTeX.com")
遂证。

**案例二。** ![x.y.(x'+y')=0](img/9261776f49c67815eadf0ef65a911355.png "Rendered by QuickLaTeX.com")
![LHS: (x.y).(x'+y')=x.x'.y+x.y.y'](img/67f129f489ed0242e488f13ba967b4b2.png "Rendered by QuickLaTeX.com")
![=0=RHS](img/e5ea0d63c41b481e822eb392c73c318a.png "Rendered by QuickLaTeX.com")
遂证成。
利用布尔代数的恒等式证明了德摩根定理。