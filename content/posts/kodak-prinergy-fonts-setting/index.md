+++
title = "Kodak Prinergy 字体配置"
author = ["Wang Jun"]
tags = ["PrePress", "Kodak", "Font", "Workflow"]
draft = false
+++

Kodak Prinergy and Preps setting Text Mark Font.

<!--more-->


## 配置本地 Preps 默认描述文件并使用 CJK 字体 {#配置本地-preps-默认描述文件并使用-cjk-字体}

1.  确认未启动 Preps ，使用记事本打开描述文件，位于 **[Local]C:\Program Files (x86)\Kodak\Preps 7\Profiles\Default\default.cfg** 。

    将如下原始的描述语句：
    ```text
    -CJK_TEXTMARKCHARACTERCOLLECTION:Adobe-Japan1-2
    -CJK_TEXTMARKENCODING:2561
    -CJK_TEXTMARKFONTENCODINGSTRING:90ms-RKSJ
    -CJK_TEXTMARKFONTNAME:Sazanami-Mincho-Regular
    -CJK_TEXTMARKFONTNAMEPREVIEW:Sazanami-Mincho-Regular
    ```
    更改为：
    ```text
    -CJK_TEXTMARKCHARACTERCOLLECTION:Adobe-GB1-4
    -CJK_TEXTMARKENCODING:256
    -CJK_TEXTMARKFONTENCODINGSTRING:UniGB-UCS2
    -CJK_TEXTMARKFONTNAME:ShanHeiSun-Uni
    -CJK_TEXTMARKFONTNAMEPREVIEW:ShanHeiSun-Uni
    ```

2.  将 CID 字体 **ShanHeiSun-Uni** 放入 **[Local]C:\Program Files (x86)\Kodak\Preps 7\RIP\Resource\CIDFont** 文件夹下。

3.  启动 Preps ，打开首选项，根据需要设置其余的配置选项并保存。


## 配置从 Workshop 启动 Preps 时使用的默认描述文件 {#配置从-workshop-启动-preps-时使用的默认描述文件}

每一次从 [Local]Workshop 启动 Preps，都默认使用 **PrepsPrinergy.cfg**

描述配置文件 **[Local]C:\Program Files (x86)\Kodak\Prinergy\AraxiPreps\Profiles\PrepsPrinergy.cfg** ，这个描述文件是 Local Workshop Preps 每次启动时从 **[Server]C:\Prinergy\CreoAraxi\AraxiPreps\Profiles\PrepsPrinergy.cfg.template** 读取的。

1.  使用记事本打开 **[Server]C:\Prinergy\CreoAraxi\AraxiPreps\Profiles\PrepsPrinergy.cfg.template** 加入如下描述：
    ```text
    -CJK_TEXTMARKCHARACTERCOLLECTION:Adobe-GB1-4
    -CJK_TEXTMARKENCODING:256
    -CJK_TEXTMARKFONTENCODINGSTRING:UniGB-UCS2
    -CJK_TEXTMARKFONTNAME:ShanHeiSun-Uni
    -CJK_TEXTMARKFONTNAMEPREVIEW:ShanHeiSun-Uni
    ```

2.  从 Workshop 启动 Preps ，打开首选项可以发现标记标签下的 CJK 字体已更改为 ShanHeiSun-Uni 。

    根据需要依次设置首选项中其余标签下的设置，并保存。

    此时的设置都被保存在了 [Local]C:\Program Files (x86)\Kodak\Prinergy\AraxiPreps\Profiles\PrepsPrinergy.cfg 中。

    使用记事本打开这个文件，复制其中的内容。

3.  使用记事本打开 [Server]C:\Prinergy\CreoAraxi\AraxiPreps\Profiles\PrepsPrinergy.cfg.template，将上一步中复制的内容进行粘帖，并保存。

4.  将 CID 字体 ShanHeiSun-Uni 分别放入如下目录内：
    -   [Local]C:\Program Files (x86)\Kodak\Prinergy\AraxiPreps\RIP\Resource\CIDFont

    -   [Server]C:\Prinergy\CreoAraxi\AraxiPreps\RIP\Resource\CIDFont

    -   [Server]C:Prinergy\AdobeExtreme\bin\Resource\CIDFont

5.  通过以上步骤，之后在 Workshop 中调用 Preps 时，默认使用的描述配置文件已设置完成。


## 导入拼版方案时应对CJK标记字体的设置 {#导入拼版方案时应对cjk标记字体的设置}

导入拼版方案时默认调用 `Import/ImportALL` 模板。

导入拼版方案模板下的导入版式模块"描述文件"有4种选择，分别是： **Default** 、 **JDF_AutoMatching**  、 **PDF**  、 **PrepsPrinergy** 对应的就是 **[Server]C:\Prinergy\CreoAraxi\AraxiPreps\Profiles** 下的描述文件，所以如果这里的描述文件不正确，导入拼版方案会失败，常见的应该是缺失字体问题。

这几个描述文件的更改可以使用如下的方法：

1.  打开位于 **[Server]C:\Prinergy\CreoAraxi\AraxiPreps\Profiles** 目录下的这些描述文件。

2.  使用记事本打开这些描述文件，分别加入如下描述语句：
    ```text
    -CJK_TEXTMARKCHARACTERCOLLECTION:Adobe-GB1-4
    -CJK_TEXTMARKENCODING:256
    -CJK_TEXTMARKFONTENCODINGSTRING:UniGB-UCS2
    -CJK_TEXTMARKFONTNAME:ShanHeiSun-Uni
    -CJK_TEXTMARKFONTNAMEPREVIEW:ShanHeiSun-Uni
    ```


## 为印能捷或演化版安装后端 CID 字体 {#为印能捷或演化版安装后端-cid-字体}

-   Prinergy 字体目录
    ```text
    \AraxiHome\AdobeExtreme\bin\Resource\CIDFont
    ```

-   Prinergy EVO 字体目录
    ```text
    C:\Program Files\Kodak\Prinergy Evo 6.0.6.0\static_data\common\Resource\CIDFont
    ```
