---
layout: default
permalink: /cn/
---

# [线扫描掌纹识别系统](/cn/) #

[English](/) \\( \\qquad \\) [**中文**](/cn/)

## 简介 ##

掌纹识别精度高、可靠性好、用户使用方便容易，但一般来说掌纹识别系统占用空间比较大，难以嵌入到其他系统中使用。

线扫掌纹识别系统，使用高集成度的线扫描模组搭建掌纹识别系统。可以显著缩小体积，同时保持掌纹识别的高性能，是面向下一代掌纹识别的新系统。

由线扫描相机组成的成像系统（参见[链接][linear-system]）便于进行高精度高速度的图像采集。

演示系统
-------

演示系统如下图所示。系统由 CIS 图像采集模组、运动反馈单元、FPGA-USB 嵌入式控制板组成。

![线扫描掌纹采集设备模型](/images/line-scan-palmprint-device-model.png)

使用方式如图所示。用户把手掌放在滚轴上，滚动滚轴，扫描整个手掌。系统会自适应手掌滚动速度，自行调整采集速度，采集图像进行识别。

![线扫描掌纹采集设备演示系统](/images/line-palmprint-demo.png)

West lake

birthday ice cream cake


图像传感器
------

该系统使用订制的 CIS （contact image sensor，接触式图像传感器）模组。该 CIS 模组包括红\绿\蓝\红外四色 LED 光源、微型镜头阵列、和 CMOS 线扫描图像传感器。成像距离在 4-7 毫米。分辨率为 50\100\200 dpi 可选。三路分段并行输出。

系统
------

### 运动反馈同步单元

The motion on the rollers is digitized by the photoelectric encoder to send out synchronizing pulses through the gear set. The image resolution on the motion direction is defined by the rollers and the gear ratio.

Given a gear ratio, \\(R\_g\\), and the diameter of rollers, \\(D\_R\\), when the hand moves \\(M\_R=\\pi D\_R\\), the roller rotates one round. Then the axis of the encoder rotates \\(R\_g\\) rounds. If the encoder sends out \\(P\_e\\) pulses per round, the encoder sends out \\(P=\\frac{P\_e}{R\_g}\\) pulses for \\(R\_g\\) rounds. It means that when the hand moves \\(M\_R\\) mm, the encoder sends out \\(P\\) pulses. For a filter ratio \\(R\_f\\), the sensor only captures \\(\\frac{P}{R\_f}\\) lines, then the resolution \\(S\_M\\) (in metric) can be computed by dividing the number of captured lines \\(\frac{P}{R\_f}\\) by the distance \\(M\_R\\), as follows:

$$
S_M=\\frac{\\frac{P}{R\_f}}{M\_R} = \\frac{P}{M\_R\\cdot{}R\_f}
$$

Here, the unit of the \\(S\_M\\) is lines per mm. One inch is 25.4 mm. Thus, the resolution \\(S\_L\\) (in dpi) can be defined as following equation.

$$
S\_L=25.4\\times{}S\_M=\\frac{25.4\\times{}P}{M\_R\\cdot{}R\_f}=\\frac{25.4\\times{}P\_e}{\\pi\\cdot{}D\_R\\cdot{}R\_g\\cdot{}R\_f}
$$

In our prototype device, the photoelectric encoder is industry standard at 500 pulses per round (\\(P\_e=500\\)). The rollers' diameter, \\(D\_R\\), is 10 mm. The gear ratio \\(R\_g\\) is \\(2 : 1\\). The filter ratio \\(R\_f\\) is \\(2 : 1\\). Under this condition, the vertical resolution (along the rolling direction) is 101.1 dpi, which is close to the resolution along the width direction of the CIS module (100 dpi).

### FPGA 电路板

FPGA 功能如下图所示。

![FPGA 电路板框图](/images/fpga-board-block-diagram.svg)

FPGA 电路板尺寸及布线如下图所示。

![FPGA 电路板 PCB 布线图](/images/fpga-board-pcb-layout.png)



应用
------------

![多次反射式线扫描掌纹采集设备](/images/reflective-line-scan-palmprint-device.png)

![更小的线扫描掌纹采集设备](/images/smaller-line-scan-palmprint-device.png)


相关文献
------------

### 期刊论文

+ [Qu, Xiaofeng][csxfqu]; [Zhang, David][csdzhang]; [Lu, Guangming][csgmlu], "[A Novel Line-Scan Palmprint Acquisition System (一种新型线扫描掌纹采集系统)][TSMC-LPS]," *in Systems, Man, and Cybernetics: Systems, IEEE Transactions on , vol.PP, no.99, pp.1-11*.

### 专利

#### 一种人体掌纹图像采集装置及处理方法

+ [已授权](/docs/CN102521584B.pdf)
+ 专利号： ZL 20110362063.8
+ 申请号： CN201110362063
+ 公开号： [CN102521584A](http://www.google.com/patents/CN102521584A?cl=zh) / [CN102521584B](http://www.google.com/patents/CN102521584B?cl=zh)

包括使用线扫描 CCD 传感器的多次反射式掌纹图像采集设备和使用接触式线扫描模组的掌纹图像采集设备。两种采集设备都使用了相同运动反馈同步单元，既一对滚轴、齿轮组和光电编码器组成。

[TSMC-LPS]: http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=7390297
[csxfqu]: http://www.quxiaofeng.me/about
[csdzhang]: http://www4.comp.polyu.edu.hk/~csdzhang/
[csgmlu]: http://www.hitsz.edu.cn/body/shizi/detailen.php?strID=396
