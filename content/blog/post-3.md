---
title: "Linux安装记"
date: 2026-02-03
description: "UEFI启动EasyBCD不能用时 无U盘Windows11安装Linux - Zorin系统 长文教程/记录"
tags: ["学习笔记", "Linux"]
authors:
  - name: "Xingyuan55"
draft: false
---


在传说中有一个系统，叫做Linux。仅存于传说中自然是不行的，于是我把 Zorin OS Linux 安装进了我的电脑，作为第二个系统。分配了16G空间给它。

本文是使用Zorin OS内置的vim编辑的（划掉，vim太难用了，用vscode）。现在还差配置github就能完全在Linux上编程了。

以下是在没有U盘的情况下从windows安装双系统的教程。

写这篇文章是因为网上的教程都不能让我直接照抄，故记录我的安装过程，顺便留给后人。

> [!IMPORTANT] 
> 确保您的系统引导方式/分区表类型是 `UEFI/GPT` 而不是 `MBR`。本文只适用于前者，后者请参阅 [无U盘win10安装Linux-Ubuntu系统 - csdn博客](https://blog.csdn.net/sinat_41870148/article/details/94232215) ，使用 EasyBCD 创建引导。
>
> 通常来说，现代的设备大概率是 `UEFI/GPT` 格式。因此您可以尝试按照这篇文章来实行。
> 

{{% steps %}}

### 0. 前导

首先下载我们想要的系统iso。这里以我安装的 [Zorin OS](http://zorin.com/os) 为例，它基于 Ubuntu。

首先我们知道，按理来说安装系统需要有以下两个东西：

- 移动介质（U盘），用于安装系统

- 将要安装系统的磁盘空间

但是显然我只有第二项，于是我需要从虚空中要来移动介质。这一部分最为关键，且安装不同Linux系统的这一步几乎一致，因此这一部分是我们的重点。我的参考文章是 [傻瓜式长文详细教程：无需u盘装系统（ubuntu、deepin双系统等）](https://blog.csdn.net/qq_34769162/article/details/108049180) 。我建议您先阅读我这篇文章。

### 1. 留出空间 创建分区

因为我们没有 U盘，因此除了 将安装系统的磁盘空间 之外，我们还需要一个分区来模拟那块U盘。

使用分区管理工具（如 Windows自带的磁盘管理 或 [DiskGenius](https://www.diskgenius.cn/) 等），进行如下操作：

1. 观察系统映像iso的大小，乘以约`1.2`（其实大小放的下iso映像应该就可以），作为“模拟U盘”的空间。在硬盘上挤出这么大空间，创建分区，文件系统选`FAT32`。为了下文方便，我们称之为`I:/`
2. 在硬盘上再挤出你想留给Linux的空间。保持空闲。

### 写入“模拟U盘” 配置UEFI启动

在Windows上，双击打开iso，全选复制到上文给模拟U盘创建的分区`I:/`。

接下来我们需要一款叫做 [EasyUEFI](https://www.easyuefi.com/index-cn.html) 的软件（15天试用版就够用），让电脑识别我们模拟的“启动U盘”

进来之后点击最左面的 **管理EFI启动项**，进取之后点中间第二个带绿加号的 **创建新项**。

其中，
1. 上面的 系统类型 从 Windows 改成 Linux
2. 描述 随便写一个，比如 `Install Zorin OS awa`
3. 下面的 磁盘/分区 那选择刚弄好的小分区`I:/`
4. 文件路径 点右侧的浏览，点进 `/efi/boot/`，找到里面的 `grub64.efi`

> 参考下图（网图，不一定和我们的一样）：
> ![/image/blog/post-3-01.jpeg]

### 关闭安全/快速启动

这一步我是没有的，因为我的电脑上压根没有这个选项。参见[别人的文章](https://blog.csdn.net/qq_34769162/article/details/108049180#%E5%85%B3%E9%97%AD%E5%AE%89%E5%85%A8/%E5%BF%AB%E9%80%9F%E5%90%AF%E5%8A%A8:~:text=efi/boot%E4%B8%8B%E9%9D%A2-,%E5%85%B3%E9%97%AD%E5%AE%89%E5%85%A8/%E5%BF%AB%E9%80%9F%E5%90%AF%E5%8A%A8,-win8%E4%B9%8B%E5%90%8E%E5%BA%94%E8%AF%A5)

### 开始安装

这一步骤的以下几点步骤各电脑可能不同。中心思想是一样的：从刚刚配置好的`I:/`启动，进入安装器

1. 关闭电脑。

2. 重新开机。在开机第一屏按按照屏幕上显示的快捷键进入启动项配置（比如我的ThinkPad，它让我`press Enter`，我就狂按回车，进入 `Startup Interrupt Menu`）

3. 选择从临时设备启动（在我的电脑上，按F12选`to Choose a temporary startup device`）

4. 我们应该能看到一项，名字就是我们刚刚填的描述，比如`Install Zorin OS awa`，选择并点进去

5. 进入安装Linux系统的临时系统。安装过程开始。

### 安装Linux

这一步是常规的安装系统过程。

我们根据引导来安装系统。有一点要注意，安装系统的位置是我们留出空闲的空间。如果您安装的系统有清晰的官方教程，请查阅官方教程，以下是我的安装选项：

> 选择空闲处，新建分区，主分区，文件系统：`ext4`，挂载点：`/`，安装启动引导器的设备：保持默认，即硬盘`/dev/nvme0n1/  UMIS RPJT....1QDQ(512.1GB)`

### 结束

安装好 Linux 后，您可以删除掉作为“模拟启动U盘”的`I:/`，它没有用了，任你处置：合并回 Windows分区 或是 合并到 Linux分区都可以。事实上 EasyUEFI 也可以卸载。


{{% /steps %}}

没了。

唉，我还得回 Windows 去 构建Hugo 和 推送git仓库（悲