---
title: Gcore-V3使用文档
weight: 1
description: 说明Gcore-V3主控转接小板的功能、使用以及元件焊接。
toc: true
authors:
tags:
categories:
series:
date: '2022-04-18'
lastmod: '2022-04-18'
draft: false
---

感谢使用Gcore-V3主控转接小板，本文档详细说明了Gcore-V3主控转接小板的功能、使用以及元件焊接。

阅读之前不妨先看视频 [罗技G613主控转接小板V3](https://gohugo.io/getting-started/installing/) 


>  **更新说明：**
	Gcore—V3版本的主控转接小板，在V2的基础上，不仅仅将键盘矩阵引脚及LS、蓝牙指示灯引出，还增加了以下板载功能：
	1、充电模块及充电指示灯；
	2、3V稳压模块；
	3、按键控制键盘背光灯打开与关闭；
	4、Fn功能。
	5、开源适配该小板的键盘主PCB原理图。

[![测试图片](https://s6.jpg.cm/2022/04/18/L9T0lr.png)](https://imagelol.com/image/L9T0lr)

Gcore—V3小板共引出45个引脚，了解各引脚的使用说明请继续往下阅读。

## 电源相关
1. 充电采用5V电源输入，输入正极接5V引脚，负极接GND；
2. 电池采用3.7V锂电池，正极接BAT，负极接GND；
3. 板载3V稳压模块，该小板接上3.7V锂电池或通上5V电源即可工作。

## 背光灯与指示灯
1. 键盘背光灯采用3528/6028单色反贴片灯，所有灯珠并联，正极接“背光灯+”，负极接GND；
2. 充电指示灯采用两颗LED或者单颗共阳RGB灯，正极接5V，负极分别接R和G，R为充电中，G为充满；
3. 大写caps、蓝牙和LightSpeed模式指示灯采用3颗LED或者单颗共阳RGB灯，正极接3V，负极分别接大写LED、蓝牙LED、LSLED。

## 按键矩阵
按键矩阵可直接参考适配Gcore—V3的立创开源原理图及键盘PCB：[G613键盘改造-搭配GcoreV3](https://gohugo.io/getting-started/installing/) 

不会看原理图的话...矩阵图如下：

|  | C0        | C1     | C2      | C3    | C4       | C5    | C6             | C7        | C8       | C9         | C10  | C11 |
|:-------:|:---------:|:------:|:-------:|:-----:|:--------:|:-----:|:--------------:|:---------:|:--------:|:----------:|:----:|:---:|
| **R0**  | Num_Enter | Num_.  | Num_3   | Num_6 | Num_+    | Num_9 | Num_-          | Num_*     | 上一曲      | 下一曲        | 音量+  | 音量- |
| **R1**  | Num_0     | Num_2  | Num_1   | Num_5 | Num_4    | Num_8 | Num_7          | Num_/     | NumLock  | 停止播放       | 暂停播放 | 静音  |
| **R2**  | 右         | 下      | 上       | PgDn  | END      | HOME  | INS            | PgUp      | PB       | SL         | PS   |
| **R3**      | 左         | R_Ctrl | R_Shift | Enter | | \ |   |  |   |        |
| **R4**      | MENU      | R_Win  | / ?     | ‘ “   | ] }      | [ {   |     |  |  | |
| **R5**      | R_Alt     | . >    | , <     | ；：    | L        | P     | O              | 0)        | 9(       | F10        | F9   |
| **R6**      | M         | N      | K       | J     | I        | U     | 8 | 7 | F8       | F7         |
| **R7**      | B         | V      | H       | G     | Y        | T     | 6 | 5 | F6       | F5         |
| **R8**      | 空格        | C      | X       | F     | D        | R     | E              | 4 | 3 | F4         | F3   |
| **R9**      | L_Alt     | L_Win  | Z       | S     | A        | W     | Q              | 2 | 1 | F2         | F1   |
| **R10**     | L_Ctrl    | G6     | L_Shfit | G5    | CAPS     | G4    | Tab            | G3        | ` ～      | G2         | ESC  | G1  |

上面矩阵图中不包含带Fn功能的按键，带Fn功能的按键（F11/F12/-_/=+/BackSpace/Delete）的接线方式请继续往下阅读。

## Fn功能
1. Fn按键说明
    
    GcoreV3主控转接小板，实现了板载Fn功能。
    
    以下为按键对应的Fn功能：
- Fn + F11 = lightSpeed按键
- Fn + F12 = 蓝牙按键
- Fn + -_  = 音量-按键
- Fn + =+  = 音量+按键
- Fn + BackSpace = 静音按键
- Fn + Delete = 开启/关闭背光灯

2. Fn功能的接线方式可参考按键矩阵原理图：[G613键盘改造-搭配GcoreV3](https://gohugo.io/getting-started/installing/) 

    不会看原理图的话...Fn功能的按键接线说明如下：

    _二极管的方向为C→R_

- 主控转接小板的n2引脚接F11按键的C脚，ROW4接F11按键的R脚；
- n2接F12按键的C脚，ROW3接F12按键的R脚；
- n3接-_按键的C脚，n5接-\_按键的R脚；
- n4接=+按键的C脚，n5接=+按键的R脚；
- n6接BackSpace按键的C脚，n7接BackSpace按键的R脚；
- n8接Delete按键的C脚，n9接Delete按键的R脚，_Delete按键的二极管位置贴0欧1206电阻或者直接短接_；
- 3V接Fn按键的C脚，n1接Fn按键的R脚，_Fn按键的二极管位置贴10欧1206电阻_。

_注意：Fn和Delete按键的二极管位置不是焊二极管！！_

***
	
## 元件焊接指引
