+++
title = "拼版中的堆叠版式"
author = ["Wang Jun"]
tags = ["Imposing"]
categories = ["PrePress"]
draft = false
+++

堆叠一般应用于数码打印，也称单面堆叠(或双面堆叠)，或者分订合装。

<!--more-->

-   堆叠

    将 `3个印张` 自上而下排列，十字裁切后将四堆重叠即可按顺序排列产品。

    {{< figure src="/images/split-and-binding-imposing/2020-06-10_09-19-41_screenshot.png" >}}

    分订合装完全可以实现更复杂的版式，比如每印张更多的页面，每个页面在每印张上有多个副本。

-   在Preps中建立分订合装的步骤
    1.  添加纸张，建立网格( `C-M` 建立,此处以 `双面堆叠` 为例，故印张使用套版印刷 `Sheetwise` ，如果是单面堆叠，则此处需要使用单面印刷 `Single-Sided` )

        {{< figure src="/images/split-and-binding-imposing/2020-06-10_09-27-51_screenshot.png" >}}

    2.  对网格重新 `编号` (根据实际需要)(如果是单面堆叠，则编号直接 `1-2-3...N` 顺次编号即可。)

        {{< figure src="/images/split-and-binding-imposing/2020-06-10_09-30-19_screenshot.png" >}}

    3.  更改 `产品属性-装订样式` 为 `单联` `Cut and Stack`

        {{< figure src="/images/split-and-binding-imposing/2020-06-10_09-34-01_screenshot.png" >}}

    4.  更改 `部件属性-计划的页面数量` 为所需要的页面数量，生成印刷运行即可完成。

        {{< figure src="/images/split-and-binding-imposing/2020-06-10_09-38-05_screenshot.png" >}}
