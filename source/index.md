.. Voron-CN-Document documentation master file, created by
   sphinx-quickstart on Wed Oct 27 02:31:17 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

# 欢迎访问 Voron中文文档!

# 目录

# 前言

这篇文章将引导大家如何构建一个Voron所需要的所有细节，和其他同类型的文章不同，这是一篇交流为主的教程，欢迎大家完善。
并尊重所有玩家基于自己场合考虑的所有方案！

当大家接触3D打印机的时候，我们需要明白一个3D打印机分为机械、电控硬件、软件程序三个部分，机械部分请参考VORON官方的文档。

电控部分又分为两个部分：应用处理器（即树莓派或者香橙派）和打印机主控板。

软件部分则主要分为三个部分：OctoPrint、Klipper、Klipper打印机固件

**安全须知**

- **3D打印机在组装的过程中涉及到220V市电，请注意操作安全，防止产生不必要的人身伤害，请注意金属外壳的可靠接地**
- **在任何时候进行维护或者调试时，请不要带电操作（除非你知道你在做什么？我已经烧了一块树莓派和一块蜘蛛主板）**
- **在打印ABS时为了防止吸入过量的VOC，建议使用预防措施（如空气过滤器）;**
- **VORON 不是为了在高温环境下打印，如果需要，请自行更改设计，原始设计不建议使用主动舱室加热器，因为这可能引发火灾**
- **如果遇到问题，请和官方社区交互，不要在网上看各种不靠谱文章和讨论**

***如果大家感兴趣，请加入QQ群605737406***

# 硬件篇

## 蜘蛛主板

我使用的是一个蜘蛛主板，它拥有8轴驱动电机，第一感觉还是非常好的，他的参数如下：

- 外观尺寸： 155.3mm X 76.5mm
- 微处理器： ARM 32-bit Cortex-M4 CPU的STM32F446（180MHz） 所有的IO口可耐受5V电压
- 输入电压：18-28VDC
- 板载输出电压： 25V-5A DC， 5V-8A（专门为树莓派，香橙派供电），3.3V-0.8A
- 电机驱动器： 8路电机驱动器
- 限位开关： 6路有源限位插座，24V/3.3V可选，可以使用各类传感器
- 输出IO： 10路可PWM输出的mosfet输出接口（1个HotBed 15A，3个Hot-End 5A，3个fans 1A，3个RGB LED strip 1A）
- 温度传感器：3pin温度传感器3路。板载4.7kOhm 0.1%上拉电阻
- 通讯接口： USB Type-C、UART、EXP1&EXP2有更多的复用功能，，如UART、I2C、CAN等
- 显示屏： 可适配LCD12864、LCD2004等显示屏

### 蜘蛛主板的电源连线

蜘蛛主板的左边我们可以看到如图所示的接线柱

[![Spider_v1.1_wiring](_static/Spider_v1.1_wiring.svg)](_static/Spider_v1.1_wiring.svg)

**请注意，24V输入永远插在PWR IN接口上，并且注意极性不要错了**

- PWR IN: 电源输入，必须提供
- BED IN： 热床24V输入，必须提供
- BED OUT: 电源输出，如果是交流热床，连接固态继电器
- E2 OUT: 输出E2挤出机加热电源
- E1 OUT: 输出E1挤出机加热电源
- E0 OUT: 输出E0挤出机加热电源（接口PB15）

如果你只有一个挤出机，那么你可以连接E0，他的端口是PB15，而BED OUT是PB4。

