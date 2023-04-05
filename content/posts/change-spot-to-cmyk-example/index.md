+++
title = "PDF文件中专色到CMYK的转换处理实例"
author = ["Wang Jun"]
tags = ["Enfocus", "Color"]
categories = ["PrePress"]
draft = false
+++

灵活应用 Enfocus Pitstop Pro将文档中的专色转换为印刷色。

<!--more-->

-   说明

    此作业包含重要的标志专色 Pantone 2767C 和 Pantone 2192C。

    由于说明书含较多专色，故不宜采用专色印刷的方式，需要将所有专色转换为CMYK进行4色印刷。

-   结论

    印刷机台已通过打样确认 P2767C 和 P2192C 对应的 CMYK 色值(铜版纸):

    1.  Pantone 2767C =&gt; C90 M75 Y16 K40

    2.  Pantone 2192C =&gt; C85 M15 Y0  K0

    3.  爆炸图页面中 主体机器图像 是否需要调色( 2020-05-07 机器图调色,机器蓝色部分的CMYK色值大约是 C100 M53 Y0 K0 )。

-   印前工作流程
    -   在 Enfocus Pitstop中自定义专色

        Acrobat Tools -&gt; Pitstop Color -&gt; Color Picker -&gt; User Color Libraries :

        | Color Name          | CMYK | Define as Spot Color | Cyan | Magenta | Yellow | Black | ICC Profile |
        |---------------------|------|----------------------|------|---------|--------|-------|-------------|
        |                     |      | alternate values     |      |         |        |       |             |
        | P2767C C90M75Y16K40 | Yes  | Yes                  | 90   | 75      | 16     | 40    |             |
        | P2192C C85M15Y0K0   | Yes  | Yes                  | 85   | 15      | 0      | 0     |             |

    -   爆炸图的作业过程
        1.  爆炸图要求的成品尺寸为430x285mm

        2.  将来稿文件中除P2767C和P2192C外的专色转换为CMYK(在AI内通过删除色板的方式)

        3.  其它细节的常规处理(页面尺寸正确 / 复黑到单色黑处理 / 出血正确等)

        4.  注意爆炸图主体机器图像的蓝色部分CMYK色值要求(调图)

        5.  另存为小版PDF文件(此时小版PDF文件中专色仅包含P2767C和P2192C)

        6.  在ID内拼大版

        7.  使用Enfocus Pitstop插件将大版PDF中的P2767C和P2192C通过 Global Change -&gt; Remap Color 功能重映射为自定义色值的对应专色

        8.  再使用 Global Change -&gt; Convert spot to CMYK 将重映射后的专色转换为CMYK

    -   说明书的作业过程
        1.  说明书要求的成品尺寸为140x216mm，来稿文件页面尺寸为139.7x215.9mm。即 :

            Media Box = Crop Box = Art Box = Trim Box = Bleed Box = 139.7x215.9mm

        2.  使用HDB PDF Tool box插件为上述处理后的文件定义左侧装订出血框

            分别定义奇数页和偶数页的出血框为143x222mm，注意出血边(奇数页在右上下三边，偶数页在左上下三边)。

            定义偶数页出血框时X偏移量的设置技巧 : 当输入宽度值后，自动生成的X偏移量为 (原始宽度值-输入宽度值)/2 [比如 (139.7-143)/2 = -1.6500],此时只需要将自动生成的X偏移量乘2即可。

            此操作之后文档的成品框为139.7x215.9,出血框为143x222mm。即:

            Media Box = Bleed Box = 143x222mm

            Crop Box = Art Box = Trim Box = 139.7x215.9mm

        3.  使用Enfocus Pitstop 插件 Global Change -&gt; Extend Bleed 功能为上述定义了出血框的文件自动延展出血.

            参数: Distance to the trim box : [0.2mm]

            Bleed to the bleed box -&gt; on

        4.  将上述处理后的文件置入ID进行格式化，导出为小版PDF。

            页面大小设置为140x216mm，出血上/下/外分别为3mm。

        5.  处理小版PDF文件页面中的复色黑对象

            使用 Enfocus Pitstop Pro -&gt; Global Changes -&gt; Standard -&gt; Color -&gt; Clean Up Black 功能。

            此功能处理复杂页面或者页面中存在大量线稿图时速度极慢，故需考虑将小版PDF文档拆分为少量页面后再使用此功能。

            此处不使用印能捷的精炼模板(精炼为灰度并保留专色模板)对复色黑进行处理是因为，如果文档中存在需要四色印刷的对象则不能使用灰度精炼模板，并且此模板不能完全将一些复色黑对象修改为单色黑对象。

        6.  若上一步中对小版PDF文件进行了分割，则注意合并后文件页数和顺序的正确性。

        7.  使用Preps拼大版。

        8.  大版PDF文件使用Enfocus Pitstop插件将P2767C和P2192C重映射为自定义的对应专色。

        9.  将上述处理后的大版PDF文件使用Enfocus Pitstop插件将文档中的所有专色转换为印刷色。

    -   说明书封面作业过程

        说明书为阴阳无线胶装，封面封底为 K+P2767C+P2192C 转换为的4色印刷，封二封三为 P2767C专色印刷，故作为正反版拼版。

        书脊上的色位是封一色位的延伸。

        1.  将以上小版PDF文件的封一单独取出，使用HDB插件在封一页面左侧定义出血框6mm(即书背6mm，内页70g双胶纸120P)，再使用Enfocus Pitstop插件的延展出血功能将将色位延伸至书背处。

        2.  将添加书背色位后的封一与小版PDF的封底置入ID拼版，2拼尺寸为444x292，作为正面印版。

        3.  在ID中将封面封底拼版删除，替换为一个444x292大小的色块填充P2767C，作业背面印版。
