+++
title = "Kindle 生词本"
author = ["Wang Jun"]
tags = ["Kindle"]
categories = ["Reading"]
draft = false
+++

生词本（Vocabulary Builder）是 Kindle 阅读器的一个原生功能。该功能由“程序”和“数据库”组成。

<!--more-->


## 生词本的用法 {#生词本的用法}

“程序”就是我们在 Kindle 中可以看到的那个叫“生词本”的东西。打开它两种方法：一种是点击右上角的菜单按钮，然后在弹出的菜单中点击“生词本”；另一种是在 Kindle 主屏中点击“生词本”项。

“数据库”就是存储单词数据的一个文件型数据库（SQLite），在 Kindle 系统中存放的绝对路径如下所示：

```text
/chroot/mnt/us/system/vocabulary/vocab.db
```

通常我们会通过 USB 数据线将 Kindle 连接到了电脑上查看其中的文件（也就是将 Kindle 设备的磁盘挂载到我们所使用的操作系统中），那么数据库文件可以在 Kindle 磁盘的根目录中找到：

```text
system/vocabulary/vocab.db
```

注意：一般情况下 Kindle 根目录中的 system 文件夹处于隐藏状态，你需要通过设置文件浏览器，让其显示隐藏文件。

平时阅读电子书时，遇到生词后，我们可以用手指划词，调取 Kindle 字典查看释义，与此同时，该词便会被自动添加到生词本的数据库中。Kindle 原生功能只有这一种往生词本中添加单词的方式。

如果绑定 Kindle 的亚马逊账户开启了 Whispersync 设备同步，生词本中收录的词汇会自动同步到云端。有的小伙伴为了清空生词本就试图删除此文件，但仅仅删除 vocab.db 这个数据库文件是无效的，即便删掉了 Kindle 仍然会从云端拉取已同步的数据。


## 清空生词本 {#清空生词本}

首先确保安装了 SQLite ，然后以命令行的方式修改 Kindle 生词本数据库文件。具体方法为，打开“命令提示符”“终端”切换到 vocab.db 所在目录。

```text
cd E:\Kindle\system\vocabulary
```

然后执行下面这两条命令即可：

```text
$ sqlite3 vocab.db 'DELETE FROM LOOKUPS'
$ sqlite3 vocab.db 'DELETE FROM WORDS'
```

这样清空 Kindle 生词本本地的词条，在联网的状态下，云端的生词会被自动清空。
