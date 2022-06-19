---
title: G84键盘使用文档
weight: 1
description: 说明G84键盘的功能、使用以及元件焊接。
toc: true
authors: SixSixFish
tags:
categories:
series:
date: '2022-06-18'
lastmod: '2022-06-18'
draft: false
---

感谢使用G84键盘，本文档详细说明了G84键盘的功能、使用、装配以及元件焊接。

阅读之前不妨先看视频 [罗技G613键盘改造 | 客制化从换轴到开厂系列](https://www.bilibili.com/video/BV14W4y167eC/) 

该键盘主PCB原理图已发布在立创开源平台：[G613键盘改造-搭配GcoreV3](https://oshwhub.com/lmlku/g613-GoreV3) 

## 配列
该配列结合了常规84配列键盘，大F minila键位布局，以及美观和个人使用习惯，整合得到以下配列。

[![G84配列图.png](https://s6.jpg.cm/2022/06/13/PLHBbT.png)](https://imagelol.com/image/PLHBbT)

## Fn按键功能

 - Fn + F11 = lightSpeed按键;
 - Fn + F12 = 蓝牙按键;
 - Fn + F1 = 音量-按键;
 - Fn + F2 = 音量+按键;
 - Fn + F3 = 静音按键;
 - Fn + F4 = 暂停按键;
 - Fn + End = 开启/关闭RGB背光灯/电量显示：

	1. 按键持续时间长于 30ms，但小于 2s， 即为短按动作，短按会打开电量指示灯，电量指示灯在亮起33秒后自动熄灭，或者双击FN+END手动关闭；
	2. 按键持续时间长于 2s， 即为长按动作， 长按会开启或者关闭RGB背光灯。
	3. 在 1s 内连续两次短按键，会关闭电量指示灯和RGB背光灯。

 - Fn + 上 = 上一个灯效。
 - Fn + 下 = 下一个灯效。
 - Fn + 右 = 灯效调速。

## 外壳和定位板

外壳可以采用群内分享的gasket结构3D打印外壳，PCB也适配常规84外壳。
外壳底部螺丝螺丝采用M2*10，铜柱采用M2*3*4.2（内径*高*外径）热熔螺母。
[![gasket结构3D打印外壳渲染图.png](https://s6.jpg.cm/2022/06/16/PLK9Ez.png)](https://imagelol.com/image/PLK9Ez)

定位板可以采用群内分享的适配gasket结构的定位板图纸。
定位板和PCB连接的螺丝采用M2*10，螺母采用M2塑胶螺母。
[![定位板渲染图.png](https://s6.jpg.cm/2022/06/16/PLKTju.png)](https://imagelol.com/image/PLKTju)

## 元件焊接指引
主PCB所需元件如下：

 元件名称 | 数量|备注
-----| ----|----|
PH2.0电池接口|1|注意正负！
Type-C 2P母座 | 1|充电接口
3528/6028RGB共阳反贴灯珠| 1|蓝牙、LS、大写指示灯；非WS2812b.
3528/6028反贴单色LED | 3|电量/充电指示灯
100欧电阻|1|1206封装
排针43P|1|连接主控小板
热插拔轴座|84|
ws2812b-3528灯珠|86|
4148二极管SOD-123|84|

主控转接小板请见：[GcoreV3主控转接小板](/docs/g613/gcorev3doc/)