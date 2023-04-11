+++
title = "Heidelberg Prinect Signa Station 建立古线装宣纸书刊拼版模板"
author = ["Wang Jun"]
tags = ["Heidelberg", "PrinectSignaStation"]
categories = ["PrePress"]
draft = false
+++

## 宣纸拼版模板 {#宣纸拼版模板}

一般地，宣纸书籍作品使用纸张为宣纸(宣纸特性决定了只能单面印刷)，之后通过折页形成书帖，装术为倒装(右侧装订)样式。

宣纸对折后将对折线作为书口，而将纸边作为装订边，故宣纸书帖一个正反面书页称为一个筒页。(类比左侧装订的折页是将对折线作为装订边，而将纸边作为书口。)

<!--more-->

-   宣纸折页

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-21_14-58-56_screenshot.png" >}}


## 版式布局 {#版式布局}

页面大小和印刷幅面允许时，一般地每印张两个筒页(一个印张通过折页两次后直接形成两个筒页)。

-   印张版式布局

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-21_15-19-50_screenshot.png" >}}


## 小版文件要求 {#小版文件要求}

-   假设最终的产品尺寸为

    `(X) 208 * (Y) 320 mm =，则将一个筒页制作为一个页面，页面尺寸为 =416 * 320 mm` (即不含出血 `2X * Y`)。

-   最终版式(版面尺寸四周各含17mm空白边距以容纳标记)尺寸计算为(单位mm):

    \\[ W = 17 + 3 + Y + 3 + 2 + 2 + 3 + Y + 3 + 17 = 2Y + 50 \\]

    \\[ H = 17 + 3 + 2X + 3 + 17 = 2X + 40 \\]


## 标记制作 {#标记制作}

-   角线(线宽为0.3mm,定位点为中心.)

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-21_16-31-09_screenshot.png" >}}

-   书帖天头折线

    在垂直方向上穿过整个页面,线宽为0.3mm.

-   套准标记
    -   水平方向(线宽为0.3mm,定位点为中心.)

        {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-21_16-26-15_screenshot.png" >}}

    -   垂直方向(线宽为0.3mm,定位点为中心.)

        {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-21_17-09-33_screenshot.png" >}}

-   帖标

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-22_09-33-19_screenshot.png" >}}

-   文本标记

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-22_09-44-31_screenshot.png" >}}


## 印版模板 {#印版模板}

角线、书帖天头折线、套准标记、文本标记均锚定到印刷区域。

-   将角线标记放置4个

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-07-08_15-40-18_screenshot.png" >}}

-   书帖天头折线

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-07-08_15-41-40_screenshot.png" >}}

-   套准标记在水平和垂直方向各放置2个

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-07-08_15-42-30_screenshot.png" >}}

-   文本标记

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-07-08_15-43-27_screenshot.png" >}}


## 折手方案 {#折手方案}

由于采用一个印张单面印刷后十字折页形成两个顺序倒装筒页的方案，故由一个筒页推出一个印张而简化出折叠模式。

1.  一个筒页

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-22_10-10-06_screenshot.png" >}}

2.  一个印张

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-22_10-10-23_screenshot.png" >}}

3.  化出一个自定义的折叠模式

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-22_10-11-47_screenshot.png" >}}


## 拼版过程参数 {#拼版过程参数}

-   过程参数

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-07-08_15-44-17_screenshot.png" >}}

-   留白参数

    {{< figure src="/images/hdb-pss-xuan-paper-book-imposing/2020-05-22_10-28-27_screenshot.png" >}}
