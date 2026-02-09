---
title: "Zorin Ubuntu 安装 Fcitx5 输入法"
date: 2026-02-03
description: "Zorin默认的ibus拼音实在不好用，于是我转到Fcitx。在谷歌拼音和搜狗拼音依赖的Fctix与系统不兼容的情况下，我们换用了fctix5,安装了fcitx5自带的拼音输入法并配置，成功输入了中文"
tags: ["学习笔记", "Linux"]
authors:
  - name: "Xingyuan55"
draft: false
---

Zorin OS 自带 iBus 框架下的拼音输入法，但是联想功能实在难用。

于是，我想换用 依赖Fcitx 的搜狗输入法，按照网上很多 “Ubuntu 安装搜狗输入法”的教程安装并配置了，但均不好使，症状为：在Fcitx配置内能看到输入法，却无法选中使用，更不用说出现候选词框来输入了。

换成谷歌输入法也是一样的症状。而我所有依赖已经安装，所有ibus残留已经卸载。这是一个很罕见的问题，网上没有关于这个的讨论和解决方案。而我成功克服了，如下。

在一切开始之前，有一个秘诀：当您电脑上的`Fcitx`（或`Fcitx5`）不能按预期工作却不知什么原因时，运行如下命令（`fcitx5`就把`fcitx`改成`fcitx5`）：

```bash
fcitx-diagnose
```

然后把输出的全文复制给AI，AI应该会给你解决方案，不能用就再来一遍或者换个AI。

### 拥抱 Fcitx5

Fcitx（Fcitx4）与 基于Ubuntu 24.04的Zorin OS18 的GNOME环境 存在底层兼容性冲突，因此我们不能使用 基于Fcitx4的谷歌拼音和搜狗拼音，而是需要使用 Fcitx5。

首先，如果您曾经安装过`Fcitx4`或搜狗拼音、谷歌拼音，请卸载