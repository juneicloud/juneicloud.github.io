+++
title = "Kodak Preps 中建立古线装宣纸书刊工作拼版模板"
author = ["Wang Jun"]
tags = ["Kodak", "Preps"]
categories = ["PrePress"]
draft = false
+++

使用 Kodak Preps 建立古线装工作模板。

<!--more-->


## 文件要求 {#文件要求}

若书籍成品尺寸为 W \* H ，则要求文件页面 TrimBox 尺寸为 (2 \* W) \* H 。


## 折叠模式 {#折叠模式}

一般地，古线装宣纸单面印刷以后，通过以下垂直十字折页，形成一个书帖。由于宣纸单面对折后正反面组成类似于一张书页的正反面，中间是空的，故一个对折页称为一个筒页。
此折叠模式折页完成后形成2个连续的筒页。

{{< figure src="/images/kodak-preps-xuan-paper-book-imposing/2022-10-17_14-11-17_screenshot.png" >}}


## 印张尺寸 {#印张尺寸}

{{< figure src="/images/kodak-preps-xuan-paper-book-imposing/2022-10-17_14-22-33_screenshot.png" >}}

一般的，古线装书籍一个折页(采用垂直十字折法)折页完成后为2个和同页。(一般一个印张含一个折页，开本过小可能有多个折页，多个折页均采用相同的折法)。

-   最终成书成品尺寸宽度为 `m` ，高度为 `n` ，则要求来稿文件的 宽度为 `2m * n` (四周可各出血 `f = 3mm or 5mm`)

-   印张宽度为 `W` ，包含版面以及放置各种标记所需的必要空间；印张高度为 `H` ，包含版面以及放置各种标记所需的必要空间，但不包含印刷咬口尺寸。

-   标记占用的空间在印张宽度上左右侧应相同，设为 `a = 空间富余时默认17mm，至少应需要5mm以上` ；

    标记占用的空间在印张高度上上下侧可相同，设为 `b = 空间富余时默认17mm，至少应需要5mm以上` 。

以一印张一个折页为例：

\\[ W = ( a + f + n + f + 2 ) \times 2 ===> 取默认值时:  W = 2n + 50 \\]

\\[ H = ( b + f + m ) \times 2 ===> 取默认值时: H = 2m + 40 \\]


## 帖标 {#帖标}

{{< figure src="/images/kodak-preps-xuan-paper-book-imposing/2022-10-17_13-49-45_screenshot.png" >}}

W : 最终成书成品尺寸宽度

A : 第一帖帖标的下侧与第一折折线之间的距离 (default value 3mm)

X : 帖标步长，即每个帖标的长度。(default value 4mm)

Y : 计划的第一阵列总帖数。( X\*Y &lt; W)

即第 Y+1 帖为阵列转换帖

=====&gt;

1.  第一阵列动态帖标 C1

    -   Type   : Collation Mark A

    -   Color  : K100

    -   Origin : Head

    -   Offset : C1 = W + A

    -   Length : XY

    -   Step   : X

    第N个帖标自身的坐标: 帖标上侧 = C1 + XN

    帖标下侧 = C1 + X(N-1)

2.  第二阵列动态帖标 C2

    -   Type   : Collation Mark A

    -   Color  : K100

    -   Origin : Head

    -   Offset : C2 = W - A - X(Y-1)

    -   Length : XY

    -   Step   : -X

    第N个帖标自身的坐标: 帖标上侧 = C2 + X(N-Y-1)

    帖标下侧 = C2 + X(N-Y)

3.  首帖识别附加帖标 C1+
    -   Type   : Collation Mark C

    -   Color  : K60

    -   Origin : Head

    -   Offset : W

    -   Length : A

    -   Step   : A

4.  末帖识别附加帖标 C1++(末帖位于第一阵列)
    -   Type   : Collation Mark C

    -   Color  : K60

    -   Origin : Head

    -   Offset : C1 + XN

    -   Length : A

    -   Step   : A

5.  末帖识别附加帖标 C2++(末帖位于第二阵列)
    -   Type   : Collation Mark C

    -   Color  : K60

    -   Origin : Head

    -   Offset : C2 + X(N-Y)

    -   Length : A

    -   Step   : -A
