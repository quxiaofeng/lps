---
layout: default
permalink: /lps/
---

# A Novel Line-Scan Palmprint Acquisition System #

## Abstract ##

Biometric recognition systems have been widely used globally. However, one effective and highly accurate biometric authentication method, palmprint recognition, has not been popularly applied as it should have been, which could be due to the lack of small, flexible and user-friendly acquisition systems. To expand the use of palmprint biometrics, we propose a novel palmprint acquisition system based on the line-scan image sensor. The proposed system consists of a customized and highly integrated line-scan sensor, a self-adaptive synchronizing unit, and a field-programmable gate array controller with a cross-platform interface. The volume of the proposed system is over 94% smaller than the volume of existing palmprint systems, without compromising its verification performance. The verification performance of the proposed system was tested on a database of 8000 samples collected from 250 people, and the equal error rate is 0.048%, which is comparable to the best area camera based systems.

## 1 Introduction ##

Biometrics, led by the fast development of imaging technologies and pattern recognition algorithms, has been utilized in complicated fields, from physical/logical access control to justice/law enforcement; from time and attendance to health care biometrics {Jain2009, Laadjel2009, Dai2011, Biometricapplications2011}. Now, the requirements of biometric systems do not only focus on a high recognition rate and robustness, but have also extended to compact, online, user-friendly, and flexible for complicated cross-disciplinary applications. For instance, hand-held fingerprint capturing devices and iris capturing devices are widely used for outdoor applications. Fingerprint sensors being integrated with laptops, fingerprint sensors being embedded in locks, iris sensors being integrated with the steel safe provide better user experience and higher security than conventional solutions. However, one of the best biometric technologies, palmprint recognition, which exhibits excellent recognition performance for the rich feature and is highly reliable under multi-spectrum light, has displayed limitations in these new features. Because of the limitations of current palmprint acquisition systems, especially the dimension of the device, the application of palmprint recognition systems is limited. For example, current palmprint recognition systems are too large to be embedded into a conventional door, and have to be installed beside the door as a standalone device.

The first online palmprint identification system was invented in 2003 {Zhang2003a}. Since then, numerous acquisition systems have been created, such as flatbed scanners capturing pressed palmprints {Ong2003, Han2003, Connie2005, Lin2005, Goh2006, Badrinath2007, Zheng2007a, Struc2008}, web camera based systems (WCBS) capturing unconstrained palmprints {Shu1998, Kumar2003, Han2007b, Ong2008, Chaudhary2009, Zhu2010, Ong2010,Aykut2013, Genovese2014}, and palmprint acquisition systems with the pegged flat platen surface capturing stable palmprints {Kong2002, Zhang2003a, Kong2003, Wong2005, Kong2006, Hao2008, Wang2008, Kong2009, Li2009, Zhang2009, Zhang2010, Zhang2010b}. These systems achieve good recognition performance. However, being limited by the imaging structure, the device dimensions of these systems cannot be reduced further. In addition, user interactions and applications were also limited by the size and the structure of the systems. For example, most palmprint acquisition systems are large, and can only be used as desktop or standalone devices.

Line-scan technique would be an ideal solution for a palmprint acquisition system. Using the line-scan technique, palmprint-capturing devices could save a great amount of space for a comfortable user interface and flexible structure without sacrificing image quality and system performance. In a line-scan sensor (also called the linear image sensor, the one-dimensional image sensor), pixels are placed in a linear array, which is different from area sensors. Because of this layout of the pixel array, the imaging structure can be simplified, and space can be saved.

The contributions of this paper are as follows.

+ We propose a novel palmprint acquisition system, which uses a line-scan sensor, specifically a contact image sensor (CIS) module. The proposed system is 94% smaller than area sensor based solutions.
+ In the proposed CIS based palmprint acquisition system, a novel synchronizing unit is designed to solve the motion synchronizing problem, which occurs when using a line-scan sensor in a palmprint acquisition system. With this unit, a CIS module could capture palmprint images adaptively when a hand rolls through the rollers.
+ The proposed palmprint acquisition system is evaluated on the merit of verification performance, with the help of conventional region of interest (ROI) extraction method and competitive coding scheme feature extraction method. The verification performance of the proposed system is comparable with current area-based ones, which is supported by the experiments on a database of 8000 images from 250 people.


![](/images/fig_webcam_1.jpg)
![](/images/fig_webcam_2.jpg)
![](/images/fig_webcam_3.jpg)

Fig. 1 Web camera based palmprint capturing devices address the illumination and tracking problems. (a) The double camera design by Han et al. {Han2007b} captures both a visible spectrum image and a near-infrared image for tracking. (b) The environment-restrained design by Goh et al. {Ong2008} protects the optical path from environmental light. (c) The closed design by Zhu and Zhang {Zhu2010} does not only protect} the optical path, but also distributes the light evenly.

This paper is organized as follows: Section {sec_review} reviews existing acquisition systems. In Section {sec_sys}, the details of the structure and each component of our line-scan palmprint acquisition system (LPS) are presented. In Section {sec_exp}, the system performance is evaluated by verification experiments. Comparisons between the proposed system and area-based systems are also presented here. Section  {sec_concl} concludes this paper.
