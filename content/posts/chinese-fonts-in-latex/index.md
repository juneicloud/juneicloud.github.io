+++
title = "XeLaTeX 中文字体"
author = ["Wang Jun"]
tags = ["LaTeX", "Font"]
categories = ["Programing"]
draft = false
+++

LaTeX 在 Windows 系统下使用系统中安装的中文字体。

<!--more-->

-   `获取Windows系统中的中文字体信息`
    ```shell
    cd ~
    fc-list :lang=zh >> font.txt
    ```
    `font.txt 片断`
    ```text
    C:/WINDOWS/fonts/FZLiBian-S02S Regular.ttf: FZLiBian\-S02S,方正隶变简体:style=Regular
    C:/WINDOWS/fonts/FZShuSong-Z01T Regular.ttf: FZShuSong\-Z01T,方正书宋繁体:style=Regular
    C:/WINDOWS/fonts/FZSTK_0.TTF: FZShuTi\-S05,方正舒体_GBK:style=Regular
    C:/WINDOWS/fonts/STFANGSO.TTF: STFangsong,华文仿宋:style=Regular
    C:/WINDOWS/fonts/FZLiuXingTi-M26S Regular.ttf: FZLiuXingTi\-M26S,方正流行体简体:style=Regular
    C:/WINDOWS/fonts/FZZXHK.TTF: FZZhengHei\-EL\-GBK,方正正纤黑_GBK:style=Regular
    C:/WINDOWS/fonts/FZLiShu II-S06S Regular.ttf: FZLiShu II\-S06S,方正隶二简体:style=Regular
    ```

-   `在LaTeX中使用中文字体`

<!--listend-->

```example
% Tex
\documentclass{ctexart}

% 使用系统中的方正舒体
\setCJKfamilyfont{fangzhengshuti}{FZShuTi}
\newcommand{\fontfzst}{\CJKfamily{fangzhengshuti}}

% 使用tex文档同目录下fonts目录内的文件名为FZCSK.TTF的字体
\setCJKfamilyfont{FangZhengCuSong}[Path=fonts/]{FZCSK.TTF}
\newcommand{\fcs}{\CJKfamily{FangZhengCuSong}}

\begin{document}
\fontfzst{测试中文}
\fcs{测试中文}
\end{document}
```
