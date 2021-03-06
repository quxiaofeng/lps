---
layout: default
---

# [Line Scan Palmprint Recognition System]({{site.baseurl}}/) #

[**English**]({{site.baseurl}}/) \\( \\qquad \\) [中文]({{site.baseurl}}/cn/)

Demo
-------

![Line Scan Palmprint Device Model]({{site.baseurl}}/images/line-scan-palmprint-device-model.png)

![Line Scan Palmprint Device Demo]({{site.baseurl}}/images/line-palmprint-demo.png)

Sensor
------

System
------

### Synchronizing Unit

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

### FPGA Board

![FPGA Board Block Diagram]({{site.baseurl}}/images/fpga-board-block-diagram.svg)

![FPGA Board PCB Layout]({{site.baseurl}}/images/fpga-board-pcb-layout.png)



Future Applications
------------

![Reflective Line Scan Palmprint Device]({{site.baseurl}}/images/reflective-line-scan-palmprint-device.png)

![Smaller Line Scan Palmprint Device]({{site.baseurl}}/images/smaller-line-scan-palmprint-device.png)


Publications
------------

### Journal

+ [Qu, Xiaofeng][csxfqu]; [Zhang, David][csdzhang]; [Lu, Guangming][csgmlu], "[A Novel Line-Scan Palmprint Acquisition System][TSMC-LPS]," *in Systems, Man, and Cybernetics: Systems, IEEE Transactions on , vol.PP, no.99, pp.1-11*.

### Patent

#### <a href="http://www.google.com/patents/CN102521584B?cl=en" target="_blank">A Human Palmprint Image Collection Apparatus and A Processing Method (in Chinese)</a>

+ Grant
+ China Patent Number: ZL 2011 0362063.8
+ China Patent [CN102521584 (A)](http://www.google.com/patents/CN102521584A?cl=en) / [CN102521584 (B)](http://www.google.com/patents/CN102521584B?cl=en)


[TSMC-LPS]: http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=7390297
[csxfqu]: http://www.quxiaofeng.me/about
[csdzhang]: http://www4.comp.polyu.edu.hk/~csdzhang/
[csgmlu]: http://www.hitsz.edu.cn/body/shizi/detailen.php?strID=396
