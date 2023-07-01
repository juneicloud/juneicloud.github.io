+++
title = "Adobe illustrator 不透明度"
author = ["Wang Jun"]
tags = ["Adobe", "illustrator"]
categories = ["PrePress"]
draft = false
+++

Adobe illustrator 中关于透明度的相关笔记以及个人理解透明度的笔记。

<!--more-->


## 不透明度 {#不透明度}

-   更改图稿不透明度

    可以改变 `单个对象` 、一个 `组` 或 `图层中所有对象` 、一个 `对象的填色或描边` 的不透明度。

    1.  选择一个对象或组（或在"图层"面板中定位一个图层），若是要更改对象的填充或描边的不透明度，选择该对象，然后在"外观"面板中选择填充或描边。

    2.  在"透明度"面板或"控制"面板中设置"不透明度"选项。

-   选择所有使用特定不透明度的对象
    1.  选择一个具有该不透明度的对象，或取消选择所有对象并在"透明度"面板中输入不透明度值。

    2.  使用菜单 `选择 > 相同 > 不透明度` 。

-   多个对象应用不透明度时的不同外观
    -   单个对象和组不透明度

        {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-14-56-37_screenshot.png" >}}

    -   如果选择一个图层中的多个对象并改变其不透明度设置，则选定对象重叠区域的透明度会相对于其他对象发生改变，同时会显示出累积的不透明度。

    -   相比之下，如果定位一个图层或组，然后改变其不透明度，则图层或组中的所有对象都会被视为单一对象来处理。只有位于图层或组外面的对象及其下方的对象可以通过透明对象显示出来。如果某个对象被移入此图层或组，它就会具有此图层或组的不透明度设置，而如果某一对象被移出，则其不透明度设置也将被去掉，不再保留。

-   为图层设置不透明度
    1.  在图层面板中定位一个图层：点击图层面板中图层右侧的定位按钮。

        {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-14-22-08_screenshot.png" >}}

    2.  定位图层后，在透明度面板中为图层设置透明度

        {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-14-28-58_screenshot.png" >}}

    3.  图层被设置不透明度后，所有这个图层内的对象（包括之后新建的对象）都会应用这个不透明度。

-   识别被添加了不透明度的图层
    1.  在图层面板中识别

        {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-14-31-57_screenshot.png" >}}

    2.  通过外观面板识别

        {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-14-38-17_screenshot.png" >}}

        从图层面板中可以看出，当前被选中的A对象处于一个被设置了不透明度的图层， `A对象` 有不透明度效果，但是在透明度面板中不能看出这一点，而在外观面板的顶层可以发现有"图层"信息，点击这行即可显示当前图层透明度的详细信息，而这个详细信息也可以通过在图层面板板定位图层后在外观面板中显示出来。

        下图指示定位图层可以在外观面板和透明度面板中显示当前定位图层所设置的不透明度信息。

        选中一个不透明度图层中的对象时，并不能在透明度面板中显示不透明度信息。

        {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-14-47-21_screenshot.png" >}}

-   透明度面板-挖空组

    `挖空组` 指防止组元素相互透过对方显示出来。其作用对象是一个编组，组内的每个成员都单独设置了不透明度。

    -   挖空组

        {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-15-32-13_screenshot.png" >}}

        选择"挖空组"选项时，将循环切换以下 3 种状态： `打开` (选中标记)、 `关闭` (无标记)和 `中性` (带有贯穿直线的方块)。

    -   当需要要编组图稿，又不想与涉及的图层或组所决定的挖空行为产生冲突时，使用 `中性` 选项。

    -   当需要确保透明对象的图层或组彼此不会挖空时，使用 `关闭` 选项。


## 不透明度叠加和正片叠底叠加 {#不透明度叠加和正片叠底叠加}


### CMYK不透明度叠加模型 {#cmyk不透明度叠加模型}

-   CMYK由颜料反射光来呈色。

-   不透明对象的颜色由其反射的颜色决定，透明对象的颜色由其透过的颜色决定。

-   位于上层的半透明CMYK对象的颜色由其 自身颜色的反射 与其透过的颜色(来自下层对象颜色的反射) 共同决定。

    {{< figure src="/images/adobe-illustrator-opacity/2020-01-04_15-27-07_screenshot.png" >}}

-   反射量

    \\[ 反射量 = 颜色值的分量\_{各层对象} \times 不透明度\_{相应层} \\]

    \\[ R\_{t} = C\_{t} \times O\_{t} \\]

    \\[ R\_{b} = C\_{b} \times O\_{b} \\]

-   下层反射光透过上层的量

    \\[ 下层反射光透过上层的量 = 下层对象的反射 \times (1 - 上层不透明度) \\]

    ```text
    (1 - 上层不透明度) 可以理解为透明的程度。
    ```

\\[ T\_{b} = R\_{b} \times (1 - O\_{t}) \\]

-   上下层叠加的最终值

    \\[ 上下层叠加的最终值 = 上层的反射 + 来自下层反射透过上层的量 \\]

    \\[ Final = R\_{t} + T\_{b} = C\_{t} \times O\_{t} + C\_{b} \times O\_{b} \times ( 1 - O\_{t} ) \\]

    即：

    \\[ 不透明度叠加 = 上层色值 \times 上层不透明度 + 下层色值 \times 下层不透明度 \times (1 - 上层不透明度) \\]


### CMYK不透明度叠加计算实例 {#cmyk不透明度叠加计算实例}

-   不透明度叠加

    {{< figure src="/images/adobe-illustrator-opacity/2020-01-04_15-51-40_screenshot.png" >}}

-   对于 `A区域` 来讲， `A区域` 无下层对象，故将 `A区域` 下层颜色值的各分量和不透明度都看作是 `0` 。所以 `A区域` 最终的透明度叠加值：

    \\[ C = 70 \times 75\\% + 0 \times 0 \times (1 - 75\\%) = 52.5 \\]

    \\[ M = 50 \times 75\\% + 0 \times 0 \times (1 - 75\\%) = 37.5 \\]

    \\[ Y = 30 \times 75\\% + 0 \times 0 \times (1 - 75\\%) = 22.5 \\]

-   对于 `B区域` 来讲， `B区域` 也无下层对象，故将 `B区域` 下层颜色值的各分量和不透明度都看作是 `0` 。所以 `B区域` 最终的透明度叠加值：

    \\[ C = 25 \times 45\\% + 0 \times 0 \times (1- 45\\%) = 11.25 \\]

    \\[ M = 35 \times 45\\% + 0 \times 0 \times (1- 45\\%) = 15.75 \\]

    \\[ Y = 15 \times 45\\% + 0 \times 0 \times (1- 45\\%) = 6.75 \\]

    \\[ K = 55 \times 45\\% + 0 \times 0 \times (1- 45\\%) = 24.75 \\]

-   对于 `C区域` ，其颜色值是 `B` (上层)的反射值与 `A` (下层)反射值透过上B的分量的叠加。所以 `C区域` 最终的透明度叠加值：

    \\[ C = 25 \times 45\\% + 70 \times 75\\% \times (1 - 45\\%) = 40.125 \\]

    \\[ M = 35 \times 45\\% + 50 \times 75\\% \times (1 - 45\\%) = 36.375 \\]

    \\[ Y = 15 \times 45\\% + 30 \times 75\\% \times (1 - 45\\%) = 19.125 \\]

    \\[ K = 55 \times 45\\% + 0 \times 75\\% \times (1 - 45\\%) = 24.75 \\]


### CMYK正片叠底计算方法 {#cmyk正片叠底计算方法}

-   各层对象透明度拼合值

    \\[ 各层对象透明度拼合值 = 各层对象色值 \times 各层对象不透明度 \\]

    \\[ S\_{t} = C\_{t} \times O\_{t} \\]

    \\[ S\_{b} = C\_{b} \times O\_{b} \\]

-   正片叠底叠加值

    \\[ 正片叠底叠加值 = 上层对象透明度拼合值 + 下层对象透明度拼合值 \times ( 1 - \frac{上层对象透明度拼合值}{100}) \\]

    \\[ Final = C\_{t} \times O\_{t} + C\_{b} \times O\_{b} \times ( 1 - C\_{t} \times \frac{O\_t}{100}) \\]


### CMYK不透明度叠加／正片叠底计算程序 {#cmyk不透明度叠加-正片叠底计算程序}

```python

def AlphaOverlay (TopColor, BottomColor, TopOpacity, BottomOpacity):
    TopAlpha = TopColor * TopOpacity / 100
    BottomAlpha = BottomColor * BottomOpacity / 100
    Rule = 1 - TopOpacity / 100
    Overlay = TopAlpha + BottomAlpha * Rule
    Overlay = float('%.2f' % Overlay)
    return Overlay

def MultiplyOverlay (TopColor, BottomColor, TopOpacity, BottomOpacity):
    TopAlpha = TopColor * TopOpacity / 100
    BottomAlpha = BottomColor * BottomOpacity / 100
    Rule = 1 - TopAlpha / 100
    Overlay = TopAlpha + BottomAlpha * Rule
    Overlay = float('%.2f' % Overlay)
    return Overlay

def GetObjectInfoLite (Prompt):
    InputInfo = input("Enter {} CMYK and alpha :".format(Prompt)).split(',')
    InputInfo = [int(i) for i in InputInfo]
    return InputInfo

TopColor = GetObjectInfoLite("the Top Object")
BottomColor = GetObjectInfoLite("the Bottom Object")

print("Top Object Color       :", TopColor)

print("Bottom Object Color    :", BottomColor)

FinalAlphaOverlay = [0, 0, 0, 0]
FinalMultiplyOverlay = [0, 0, 0, 0]

for i in range(4):
    FinalAlphaOverlay[i] = AlphaOverlay(TopColor[i], BottomColor[i], TopColor[4], BottomColor[4])
    FinalMultiplyOverlay[i] = MultiplyOverlay(TopColor[i], BottomColor[i], TopColor[4], BottomColor[4])

print("Alpha Overlay Color    :", FinalAlphaOverlay)
print("Multiply Overlay Color :", FinalMultiplyOverlay)
```


## 不透明蒙版 {#不透明蒙版}

-   不透明蒙版

    可以透过不透明蒙版（也称为被蒙版的图稿）提供的形状来显示其他对象。

    {{< figure src="/images/adobe-illustrator-opacity/2019-06-25-16-01-09_screenshot.png" >}}

    `蒙版对象` 定义了透明区域和透明度。 `可以将任何着色对象或栅格图像作为蒙版对象。`

    Illustrator 使用蒙版对象中 `颜色的等效灰度` 来表示蒙版中的不透明度。

    -   如果不透明蒙版为白色（如图中的字母A的白色描边），则会完全显示图稿。

    -   如果不透明蒙版为黑色，则会隐藏图稿。蒙版中的灰阶会导致图稿中出现不同程度的透明度。

    创建不透明蒙版时，"透明度"面板中被蒙版的图稿缩览图右侧将显示蒙版对象的缩览图。

    默认情况下，将链接被蒙版的图稿和蒙版对象（面板中的缩览图之间会显示一个链接）。移动被蒙版的图稿时，蒙版对象也会随之移动；而移动蒙版对象时，被蒙版的图稿却不会随之移动。可以在"透明度"面板中取消蒙版链接，以将蒙版锁定在合适的位置并单独移动被蒙版的图稿。

    可以在 Photoshop 和 Illustrator 之间移动蒙版。Illustrator 中的不透明蒙版在 Photoshop 中会被转换为图层蒙版，反之亦然。

-   创建不透明蒙版
    -   将现有对象转换为不透明蒙版

        选择至少两个对象或组，然后从"透明度"面板菜单中选择"建立不透明蒙版"。最上方的选定对象或组将用作蒙版。

    -   直接创建不透明蒙版

        选择一个对象，然后双击透明度面板中的右侧缩览图，则会创建一个空蒙版并进入蒙版编辑模式。在蒙版编辑模式手动绘制出蒙版（类比于上例中生成 `字母A` 的过程。）

-   不透明蒙版注意事项

    无法在处于蒙版编辑模式时进入隔离模式，反之亦然。

    "`剪切`"选项会将蒙版背景设置为黑色。因此，用来创建不透明蒙版且已选定"`剪切`"选项的黑色对象，如黑色文字，将不可见。若要使对象可见，请使用其他颜色，或取消选择"剪切"选项。

-   剪切或反相不透明蒙版
    -   `剪切`

        为蒙版指定黑色背景，以将被蒙版的图稿裁剪到蒙版对象边界。取消选择"剪切"选项可关闭剪切行为。要为新的不透明蒙版默认选择剪切，请从"透明度"面板菜单中选择"新建不透明蒙版为剪切蒙版"。

    -   `反相蒙版`

        反相蒙版对象的明度值，这会反相被蒙版的图稿的不透明度。

        例如，90% 透明度区域在蒙版反相后变为 10% 透明度的区域。取消选择"反相蒙版"选项，可将蒙版恢复为原始状态。

        要默认反相所有蒙版，从"透明度"面板菜单中选择"新建不透明蒙版为反相蒙版"。

-   编辑不透明蒙版对象

    可以编辑蒙版对象以更改蒙版的形状或透明度。

    -   单击"透明度"面板中的蒙版对象缩览图（右缩览图）。

    -   按住 `Alt` 并单击蒙版缩览图以隐藏文档窗口中的所有其他图稿。（如果未显示这些缩览图，从面板菜单中选择"显示缩览图"。）

    -   使用任何 Illustrator 编辑工具和技巧来编辑蒙版。

    -   单击"透明度"面板中被蒙版的图稿缩览图（左缩览图）以退出蒙版编辑模式。
