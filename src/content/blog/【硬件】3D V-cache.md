---
title: '【硬件】3D V-cache'
pubDate: 'Jul 14 2024'
heroImage: '/blog-placeholder-4.jpg'
description: '3D V-cache'
---

# 3D V-cache 的缘由

很明显，现在 IPC 是处理器升级的瓶颈，提高 IPC 有以下几个方法：

- 架构

- 制程

- 规模

很明显，制程 5nm 已经极高了，而架构中 IF 总线速度堪忧而受制于 AMD 维持价格的方法——小芯片设计而无法提升，因此，必须改进规模，而规模主要受到核心和缓存命中率的影响，而多核心会导致成本（价格）的飙升，这一点从线程撕裂者可以看到。

***所以，AMD 会选择缓存命中率。***

# 3D V-cache 的设计

在 CPU 的 CCD 中堆叠一个晶圆，就是 3D V-cache。这个晶圆中包含海量的 L3 缓存，可以大幅提高缓存命中率以减少向内存中访问的次数，提升了 IPC，也弥补了 IF 总线的低速度。

例如图中左侧 Die

![](/7950x3d.jpg)

# 3D V-cache 的实际运用

Zen 3 开始的中高端处理器都有 3D V-cache 的版本，以 `X3D` 结尾，***3D V-cache 不是标配！***

但是，两个 CCD 的型号只有一个 CCD 配备 3D V-cache，如下图右侧 CCD 没有配备 3D v-cache

![](/7950x3d.jpg)

这是因为 3D V-cache 会影响热量散发，所以，为了频率，不能全部配 3D V-cache。

不同于 Intel 的大小核差距大，依赖 Windows 调度，3D V-cache 差距小，可以用 Xbox 软件调度，如果调度失败，也无伤大雅，不会造成太大的性能影响。