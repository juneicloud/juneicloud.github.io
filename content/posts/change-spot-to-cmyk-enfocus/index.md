+++
title = "Enfocus PitStop Pro 专色转换为印刷色"
author = ["Wang Jun"]
tags = ["Enfocus", "Color"]
categories = ["PrePress"]
draft = false
+++

-   在Pitstop Pro中可以使用使用 `Global Changes --> Standard --> Color --> Convert SPot to CMYK` 功能将专色转换为CMYK。

<!--more-->

1.  Covert Spot to CMYK

    {{< figure src="/images/change-spot-to-cmyk-enfocus/2020-05-25_09-19-47_screenshot.png" >}}

    在转换过程中, `专色自身定义时的色值` 会影响到最终转换后的CMYK色值。

2.  专色的定义

    名称同为 `PANTONE Green C` 的专色，使用不同的CMYK色值定义。

    {{< figure src="/images/change-spot-to-cmyk-enfocus/2020-05-25_09-29-13_screenshot.png" >}}

    那么使用Pitstop Pro将专色转换为CMYK后，两种不同定义的 `PANTONE Green C` 的CMYK值就是不相同的，并且使用定义专色时的颜色值，即专色自身定义的色值会影响到最终转换后的CMYK数值。

    所以如果需要将文档中的一个专色转换为CMYK并且CMYK色值由自定义决定，就可以利用这一特性。

    -   先自定义一个专色，色值使用我们最终需要的CMYK值定义(即自定义一种使用CMYK颜色模式的专色)，之后将文档中的专色映射到自定义的专色，最后将专色转换为印刷色。

3.  以上过程中Pitstop Pro中的实现过程
    -   自定义专色

        使用 Color Picker 工具

    -   将文档中的专色映射到自定义专色

        使用 Global Changes 中的 Remap Colors 功能

    -   将专色转换为印刷色

        使用 Global Changes 中的 Convert Spot to CMYK 功能
4.  在Pitstop Pro中使用 Color Picker 工具自定义专色
    1.  Color Picker

        {{< figure src="/images/change-spot-to-cmyk-enfocus/2020-05-25_09-09-13_screenshot.png" >}}

        根据实际情况输入自定义专色的名称、自定义专色使用的颜色模型、色值等参数。

    2.  定义专色

        {{< figure src="/images/change-spot-to-cmyk-enfocus/2020-05-25_09-15-15_screenshot.png" >}}

        建立的专色即可保存在自定义颜色库 `User Color Libraries` 中备用。

5.  Remap Colors 将一种专色映射到另一种专色
    1.  使用 `Global Changes --> Standard --> Color --> Remap Colors`
        -   `Remap -> Channel -> Spot Color` : 选择文档中需要转换的原始专色

        -   `To -> Spot Color` : 选择自定义的专色

        -   `Overprint` : 根据需要进行选择

    2.  映射专色

        {{< figure src="/images/change-spot-to-cmyk-enfocus/2020-05-25_09-52-29_screenshot.png" >}}

6.  Remap Colors
    -   What it does? Remaps unwanted original colors to the desired colors taking into account the specified overprint settings.

    -   How to proceed
        1.  Under `Remap`. Select the appropriate option:
            -   `Color`

            -   `Color Space`

            -   `Color Range`

            -   `Channel`

        2.  Proceed as follows:
            -   `If you have chosen Color`:
                -   To use the color of a previously selected object,click the Grab Color Button -&gt; `Grab Fill` or `Grab Stroke`.

                -   To select a color from the color library,click the Pick Color Button and choose the desired color.The selected color will be shown below the button.

                -   To select Device Gray,RGB or CMYK,or calibrated gray or RGB,select the appropriate option from the list and use the sliders to select the required color variant.

            -   `If you have chosen Color Space or Channel`:
                -   Choose the appriopriate color space or channel from the list.

            -   `If you have chosen Color Range`:
                1.  Select the desired color space.

                2.  Enter the appropriate values to define the color range(From and To)

        3.  Under `To`, Select the target color or select `Keep`.

        4.  Select the appropriate overprint setting:
            -   To not change andy overprint settings,select `Keep`.

            -   To change all overprint settings to "On",select `On`.

            -   To change all overprint settings to "Off",select `Off`.
