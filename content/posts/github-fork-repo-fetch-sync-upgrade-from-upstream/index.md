+++
title = "Github fork repo fetch sync upgrade from upstream"
author = ["Wang Jun"]
tags = ["Git"]
categories = ["Programing"]
draft = false
+++

## Fork repo from upstream {#fork-repo-from-upstream}

{{< figure src="/images/github-fork-repo-fetch-sync-upgrade-from-upstream/2021-05-18_21-32-09_screenshot.png" >}}

<!--more-->


## Clone repo from self repo {#clone-repo-from-self-repo}

```shell
cd ~
git clone https://github.com/sxjune/emacs.d.git .emacs.d
```


## Repo Sync from upstream {#repo-sync-from-upstream}


### 查看仓库远程信息 {#查看仓库远程信息}

```shell
cd ~/.emacs.d/
git remote -v
```

{{< figure src="/images/github-fork-repo-fetch-sync-upgrade-from-upstream/2021-05-18_21-36-55_screenshot.png" >}}


### 添加远程仓库地址 {#添加远程仓库地址}

```shell
git remote add upstream https://github.com/purcell/emacs.d.git
git remote -v
```

{{< figure src="/images/github-fork-repo-fetch-sync-upgrade-from-upstream/2021-05-18_21-38-26_screenshot.png" >}}


### 从源仓库更新同步代码 {#从源仓库更新同步代码}

```shell
git fetch upstream
```

{{< figure src="/images/github-fork-repo-fetch-sync-upgrade-from-upstream/2021-05-18_21-39-38_screenshot.png" >}}


### 合并到本地 {#合并到本地}

```shell
git merge upstream/master
```

{{< figure src="/images/github-fork-repo-fetch-sync-upgrade-from-upstream/2021-05-18_21-40-24_screenshot.png" >}}


### 向自己的远程仓库推送合并的代码 {#向自己的远程仓库推送合并的代码}

```shell
git push origin master:master
```

{{< figure src="/images/github-fork-repo-fetch-sync-upgrade-from-upstream/2021-05-18_21-41-01_screenshot.png" >}}
