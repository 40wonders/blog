---
layout: post
title:  威胁建模
date:   2020-03-16 19:06:00 +0800
categories: security
---

最近公司在推行SDL (Security Development Lifecycle)，其中有一个项目是threat modeling，所以稍微研究了一下。

By [wikipedia definition](https://en.wikipedia.org/wiki/Threat_model)，威胁建模是：
> a process by which potential threats, such as structural vulnerabilities or the absence of appropriate safeguards, can be identified, enumerated, and mitigations can be prioritized.

所以可以想到，完成威胁建模必然需要以下几步：
1. 画出系统在用户场景中的diagram，其中要标出：
   * 所有的系统component
   * 与系统component有交互的另一方
   * 数据在系统中如何流动
   * 数据在系统中如何存储
   * 信任边界
2. 对diagram中的每个部分，分析可能有哪些威胁。分析方法有几种，如STRIDE、VAST等。
3. 对可能存在的每个威胁，评估优先级，以及如何避免或者缓解。

下面是一个典型的Web application的威胁模型。网络设备会更加复杂，因为除了提供Web interface之外，还常常与其它设备通过各种网络协议进行通信，这大大增加了attack surface。
![Example of Threat Model](/blog/assets/img/threat_model_example.png)
