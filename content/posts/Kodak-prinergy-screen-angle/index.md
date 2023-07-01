+++
title = "印能捷流程输出客户自定义加网角度"
author = ["Wang Jun"]
tags = ["Kodak", "Workflow"]
categories = ["PrePress"]
draft = false
+++

<!--more-->

1.  找到印能捷服务器 C:\Prinergy\AdobeExtreme\bin\CreoScreens\Config 路径下的 Creo_SCDV.cfg 文件，用系统记事本工具打开该文件。

    {{< figure src="/images/Kodak-prinergy-screen-angle/2023-05-11_15-15-10_screenshot.png" >}}

2.  在Creo_SCDV.cfg文件中，用下面格式添加客户自定义的加网角度。

    &lt;Screen System Name&gt;, &lt;angleC&gt; &lt;angleM&gt; &lt;angleY&gt; &lt;angleK&gt;

    例如：3D_Screen_CMYK，  6   36   66   81

    然后重启输出JTP或重启印能捷系统，印能捷输出模板就可以选到新设置的加网网角。

    {{< figure src="/images/Kodak-prinergy-screen-angle/2023-05-11_15-15-15_screenshot.png" >}}

3.  调用新设置的客户自定义角度模板输出，输出信息显示加网应用了指定的加网角度。

    {{< figure src="/images/Kodak-prinergy-screen-angle/2023-05-11_15-15-20_screenshot.png" >}}

    在CMYK分色中三个分色版角度要求相差30°或60°，第四个分色的加网角度可以是任意角度，如果客户自定义加网角度无法满足三个分色版角度相差30°或60°，需要定义两套或三套自定义加网角度参数，通过分次递交来完成四色分色版输出。
