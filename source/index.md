.. Voron-CN-Document documentation master file, created by
   sphinx-quickstart on Wed Oct 27 02:31:17 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

# 欢迎访问 Voron中文文档!

.. toctree::
   :maxdepth: 3
   :caption: Contents:



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
