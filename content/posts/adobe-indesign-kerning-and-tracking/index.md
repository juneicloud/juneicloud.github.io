+++
title = "Adobe InDesign 中的字偶间距和字符间距"
author = ["Wang Jun"]
tags = ["Adobe", "InDesing", "Design", "Font"]
categories = ["PrePress"]
draft = false
+++

## 关于字偶间距和字符间距 {#关于字偶间距和字符间距}

`字偶间距` 是增加或减少特定字符对之间间距的过程。

`字符间距` 是加宽或紧缩文本块的过程。

字偶间距和字符间距的值会影响中文文本，但一般说来，这些选项用于调整罗马字符之间的间距。

<!--more-->


### 字偶间距的类型 {#字偶间距的类型}

可以使用=原始=设定字偶间距或=视觉=字偶间距来自动微调文字的字距。原始设定字偶间距使用大多数字体附带的字偶间距对。

字偶间距对包含有关特定字母对间距的信息。其中包括：LA、P.、To、Tr、Ta、Tu、Te、Ty、Wa、WA、We、Wo、Ya 和 Yo。

默认情况下，InDesign 使用 `原始` 设定字偶间距，以便在导入或键入文本时，特定的字符对能够自动进行字偶间距调整。若要 `禁用原始设定字偶间距` ，请选择"`0`"。

视觉字偶间距调整根据相邻字符的形状调整它们之间的间距，最适合用于 `罗马字形` 中。某些字体包括完善的字距微调对规范。不过，如果某一字体仅包含极少的内建字偶间距调整或根本不包含这些内容，或者同一行的一个或多个单词使用了两种不同的字形或大小，则可能需要对文档中的罗马字文本使用视觉字偶间距调整选项。

-   视觉字偶间距

    {{< figure src="/images/adobe-indesign-kerning-and-tracking/2019-11-25_21-54-05_screenshot.png" >}}

也可以使用 `手动` 字距微调，此功能非常适合用于调整两个字母之间的间距。字距调整和手动字距微调是 `累积` 的，因此，可以首先调整个别字母对，然后收紧或放宽文本块，而不会影响字母对的相对字距微调。

单词的字偶间距不同于"字符间距"对话框中的"单词间距"选项， `单词的字偶间距` 仅更改特定单词的第一个字符与该字符前的空格之间的字偶间距值。

-   字偶间距和字符间距

    {{< figure src="/images/adobe-indesign-kerning-and-tracking/2019-11-25_21-54-39_screenshot.png" >}}


### 如何度量字偶间距和字符间距 {#如何度量字偶间距和字符间距}

可以对选定文本应用字偶间距、字符间距或同时应用这两者。

字距调整和字距微调的度量单位都是 `1/1000 em` ，这是一种相对测量单位，以当前的全角字宽作为参考单位。 `在 6 点大小的字体中，1 em（即 1 个全角字宽）等于 6 点；在 10 点的字体中，1 em 等于 10 点。` 字距微调和字距调整与当前的文字大小成严格比例。

字距调整和手动字距微调是累积的，因此，可以首先调整个别字母对，然后收紧或放宽文本块，而不会影响字母对的相对字距微调。

当通过单击在两个字母间置入插入点时，InDesign 会在"字符"面板和"控制"面板中显示字偶间距值。括号中将显示度量标准字距微调和视觉字距微调值（或定义的字距微调对）。同样，如果选择一个单词或一段文本，则 InDesign 会在"字符"面板和"控制"面板中显示字符间距值。


## 将字偶间距应用于文本 {#将字偶间距应用于文本}

可以应用以下任一类型的自动字偶间距：

`原始` 设定的字偶间距或 `视觉` 字偶间距，也可以 `手动` 调整字母间距。


### 使用原始设定的字偶间距 {#使用原始设定的字偶间距}

1.  在希望进行字符对字偶间距调整的字符间设置文本插入点，或选择文本。

2.  在"字符"面板或"控制"面板中的"字偶间距" 菜单中，选择"`原始设定`"。

3.  在"字符"面板或"控制"面板中的"字偶间距"菜单中，选择"原始设定"或"`原始设定 - 仅罗马字`"。

如果将"原始设定"应用于不含字符对字偶间距信息的字体（包括一些日文 OpenType 字体），则每个字符的间距都将设置为"0"，并且不紧缩字符。

若要避免将字体的内建字偶间距信息用于选定文本，在"字偶间距"菜单中选择"0"。

默认设置为"原始设定 - 仅罗马字"。

-   当"原始设定 -- 仅罗马字"应用于罗马 OpenType 字体时，字偶间距将与选中"原始设定"时相同。

-   当"原始设定 -- 仅罗马字"应用于 CJK OpenType 字体时，将仅对罗马字使用字偶间距字符对进行字偶间距调整，就像设置了"原始设定"时一样。

-   不会对 CJK 字符进行字偶间距调整，就像设置了"0"时一样。因此，选择"0"可关闭字偶间距调整。

如果在日文 OpenType 字体中使用字体公制字字偶间距，建议从"控制"面板菜单中选择"OpenType"&gt;"使用等比公制字"。这样，可避免进行不必要的手动字偶间距调整。


### 使用视觉字偶间距 {#使用视觉字偶间距}

1.  在要进行字偶间距调整的字符间设置文本插入点，或选择要进行字偶间距调整的文本。

2.  在"字符"面板或"控制"面板中的"字偶间距" 菜单中，选择"视觉"。

视觉字偶间距是以罗马字形式为基础设计的。可以将该功能用于 CJK 字体，但一定要检查操作的结果。


### 手动调整字偶间距 {#手动调整字偶间距}

1.  使用"文字工具"，单击以便在两个字符间置入一个插入点。

    如果选择了一段文本，则无法手动对该文本进行字偶间距调整（只可以选择"原始设定"、"视觉"或"0"）。此时可以改用字符间距调整。

    如果选择了一段文本，则无法手动对这些文本进行字偶间距调整（仅可以选择"原始设定"、"原始设定 - 仅罗马字"、"视觉"或"0"）。此时可以改用字符间距调整。

2.  执行以下操作之一：
    -   在"字符"面板或"控制"面板的"字偶间距"菜单中，键入或选择一个数值。

    -   按 Alt+左/右箭头 (Windows) 或 Option+左/右箭头 (Mac OS) 可减小或增大两个字符之间的字距微调。

字偶间距的调整量与"单位和增量首选项"对话框中的"字偶间距"值相同。按下快捷键并按住 Ctrl 键或 Command 键时，字偶间距调整量等于"字偶间距"首选项值的 5 倍。


### 更改默认字偶间距增量值 {#更改默认字偶间距增量值}

在"`首选项`"对话框的"`单位和增量`"部分中，为"`字偶间距`"选项键入一个新值，然后单击"确定"。


### 关闭选定文本的字偶间距 {#关闭选定文本的字偶间距}

1.  选择文本。

2.  在"字符"面板或"控制"面板中的"字偶间距"菜单中，键入或选择 `0` 。

还可以通过按下 `Alt+Ctrl+Q` ， `重置字偶间距和字符间距` 。执行此操作后，无论以前应用的是哪个字偶间距选项，系统都会将字偶间距设置为"`原始设定`"。


### 调整字距调整 {#调整字距调整}

1.  选择一定范围的字符。

2.  在"字符"面板或"控制"面板中，为"字符间距" 键入或选择一个数值。


### 突出显示包含自定字偶间距和字符间距的文本 {#突出显示包含自定字偶间距和字符间距的文本}

在有些情况下，需要知道应用了自定字偶间距和字符间距的文本。如果选择了"`自定字符间距/字偶间距`"首选项，则会以 `绿色` 突出显示包含自定字符间距或字偶间距的文本。

1.  选择 `“编辑”>“首选项”>“排版”` 。

2.  选择 `“自定字符间距/字偶间距”` ，然后单击"确定"。


## 调整单词间的字偶间距 {#调整单词间的字偶间距}

使用"`文字工具`" 选择一段文本，然后执行以下操作之一：

-   要在选定单词间添加 `空格` ，按 `Alt+Ctrl+\` 。

-   要删除选定单词间的 `空格` ，按 `Alt+Ctrl+Backspace` 。

-   要将字偶间距的值增大至原来的 5 倍，在按下键盘快捷键的同时，按下 `Shift` 。