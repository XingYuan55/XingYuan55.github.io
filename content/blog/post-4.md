---
title: "Zorin Ubuntu 安装 Fcitx5 输入法"
date: 2026-02-03
description: "Zorin默认的ibus拼音实在不好用，于是我转到Fcitx。在 谷歌拼音和搜狗拼音 依赖的Fctix与系统不兼容的情况下，我们换用了fctix5,安装了fcitx5自带的拼音输入法并配置，成功输入了中文"
tags: ["学习笔记", "Linux"]
authors:
  - name: "Xingyuan55"
draft: false
---

### 导言

基于Ubuntu 24.04的 Zorin OS 自带 iBus 框架下的拼音输入法，但是联想功能实在难用。

于是，我想换用 依赖Fcitx 的搜狗输入法，按照网上很多 “Ubuntu 安装搜狗输入法”的教程安装并配置了，但均不好使，症状为：在Fcitx配置内能看到输入法，却无法选中使用，更不用说出现候选词框来输入了。

换成谷歌输入法也是一样的症状。而我所有依赖已经安装，所有ibus残留已经卸载。这是一个很罕见的问题，网上没有关于这个的讨论和解决方案。而我成功克服了，如下。

在一切开始之前，有一个秘诀：当您电脑上的Fcitx5（或Fcitx）不能按预期工作却不知什么原因时，运行如下命令

```bash
fcitx5-diagnose

# 若安装的是fcitx(fcitx4):
fcitx-diagnose
```

然后把输出的全文复制给AI，AI应该会给你解决方案，不能用就再来一遍或者换个AI。

---
首先请设置系统语言为汉语。如果存在多种语言，请将汉语排在第一位。


### 拥抱Fcitx5

Fcitx5 是一个用于 Linux 的输入法框架，为输入法引擎提供依赖支持。

#### 安装

Fcitx（Fcitx4）与 Zorin OS18 的 GNOME 环境存在底层兼容性冲突，因此我们不能使用基于Fcitx4的谷歌拼音和搜狗拼音等，而是需要使用 Fcitx5。如果您不知道我这一句在讲什么，请忽略。

> [!IMPORTANT]
>
> 如果您曾经安装过`Fcitx4`或搜狗拼音、谷歌拼音，请卸载。
> ```bash
> sudo apt purge "fcitx" "fcitx*" "sogoupinyin" "sogou*" -y
> rm -rf ~/.config/fcitx ~/.cache/fcitx ~/.config/sogou*
> sudo apt autoremove --purge -u
> ```

下面开始安装。

以下命令安装 Fcitx5 核心、中文输入法、配置工具：

```bash
sudo apt install fcitx5 fcitx5-chinese-addons fcitx5-frontend-gtk3 fcitx5-frontend-qt5 fcitx-configtool fcitx5-config-qt -y
```

如果您使用的是`GNOME`桌面环境，还需要安装托盘支持：
```bash
sudo apt install gnome-shell-extension-appindicator -y
```

#### 环境变量

我们还需要配置环境变量。在环境变量文件（通常为`/etc/environment`文件）中添加：
```bash
XIM=fcitx5
XIM_PROGRAM=fcitx5
GTK_IM_MODULE=fcitx5
QT_IM_MODULE=fcitx5
XMODIFIERS=@im=fcitx5
SDL_IM_MODULE=fcitx5
GLFW_IM_MODULE=fcitx5
```

> [!NOTE]
>
> 刚刚我采用的是这篇[我参考的教程](https://zhuanlan.zhihu.com/p/597764721)（[csdn亦有发布](https://blog.csdn.net/GaaraZ/article/details/128618441)）中的配置环境变量的方法。
> 
> 但在不同教程中，对这一步的描述不同。
> 
> 例如[这篇教程](https://www.cnblogs.com/yulisuo/p/18887524)提到在`.bashrc`文件中配置：
>
> ```bash
> # .bashrc
> # fcitx5 input
> export XMODIFIERS=’@im=fcitx5’
> export XMODIFIER=’@im=fcitx5’
> export GTK_IM_MODULE=fcitx
> export QT_IM_MODULE=fcitx5
> export DefaultIMModule=fcitx5
> ```
> 
> 又例如[这篇教程](https://zhuanlan.zhihu.com/p/508797663)让我们在`~/.bash_profile`或`/etc/profile`配置。
> 
> 如果您对这一步有疑惑，请参阅其他人的教程。
> 

保存文件后，使用如下命令使配置生效：
```bash
source /etc/environment
```

然后重启计算机或注销登录。

### Xorg会话

截至目前，我们已经成功安装了`fcitx5`及配套的中文输入法。

在重启之后，您应该能够：
- 看到任务栏有小键盘图标
- 按`Ctrl + Space`切换输入法
- 能在输入法菜单中选择 拼音 输入法

如果您能正常输入汉字，且使用时无Bug,则本节按理来说可以跳过。

若不能，请继续阅读本节。

fcitx在 Wayland 会话下基本残废（作者亲测：fcitx5也残废）。如果您正在使用 Wayland 会话环境，我们必须切换到 Xrog 会话。

> [!TIP]
> 如果您想证实这一点，可以像导言所述一样，运行：
> ```bash
> fcitx5-diagnose
> ```
> 然后在输出中尝试找到这一行：
> ```bash
> WARNING: Running setxkbmap against an Xwayland server
> ```

做法是：
1. 注销当前用户登录
2. 在登录界面，点击用户名旁边的或在屏幕右下角的 齿轮图标
3. 选择 带 `Xorg` 字样的选项，如 `Zorin Desktop on Xorg`
4. 登录进来
5. 然后：
   ```bash
   fcitx6 -r
   ````

现在托盘里应该出来了，输入法也能用了。

如果再不好使，就按导言所说，运行`fcitx5-diagnose`然后把输出给AI寻求帮助。

### 开机自启

截至现在你应该已经能够使用 Fcitx5 的 拼音输入法 了。接下来还差最后一步：配置开机自动启动。

不想配置也可以，在应用启动屏幕您可以找到 Fcitx5 应用，每次开机启动一下就好。

:TODO
我还没配置开机自启，这一部分待完善。

