---
title: WS2812-RGB灯珠控制芯片说明文档
weight: 1
description: 说明WS2812-RGB灯珠控制芯片的功能、使用以及PCB集成。
toc: true
authors: SixSixFish
tags:
categories:
series:
date: '2022-04-22'
lastmod: '2022-04-22'
draft: false
---

该芯片烧录了大约120种灯效，可支持控制400颗WS2812-RGB灯珠的灯带。

使用之前不妨先看视频 [BiliBili](https://gohugo.io/getting-started/installing/) 
## 使用说明
 1. 每个灯串最多可Din-Dout串接400颗WS2812灯珠。
 2. 总共约120种灯效。
 3. 三个功能按键：上一灯效、下一灯效、调速。
 4. 同时按下“上一灯效”和“下一灯效”两个按键触发循环灯效，从第一个灯效开始循环，自动变化模式，循环过程中按下“下一灯效”结束循环，并停留在第一个灯效。
 5. 调速按键可以调节变幻速度，由慢到快共8级速度，调到最快再按下“调速”按键会回到最慢速度。
 6. 带有掉电保持功能，在使用过程中如果意外断电，会保存当前灯效和速度，下一次启动时自动使用上次的灯效与速度。
 7. 工作电压:3.2V-5V。
 8. 5V输入下，1颗WS2812-3528 RGB灯珠的功耗约为7mA。

如果想将该模块集成到自己的PCB上，请访问立创开源链接 [WS2812-RGB灯珠控制模块](https://oshwhub.com/lmlku/ws2812-rgb-modules) 

暂未发布，敬请期待...

