---
id: vserver-vnc
title: "VPS: VNC (Virtual Network Computing) console"
description: Information about the VNC console for VPSs at ZAP-Hosting - ZAP-Hosting.com documentation
sidebar_label: VNC console
services:
  - vserver
---

import InlineVoucher from '@site/src/components/InlineVoucher';

## Introduction

VNC (Virtual Network Computing) is a software that displays the screen content of a remote computer on a local computer and in return sends keyboard and mouse movements of the local computer to the remote computer. This allows you to access your server remotely even if it is not up and running properly. 

In case of startup or network problems you still have the possibility to access the system and take countermeasures. 

<InlineVoucher />


## Use of VNC
The VNC web client can be found in the VPS / Root server dashboard. To do this, click on the serial console option in the tools section of the administration and then open the VNC connection via the **Start VNC tunnel** button. 

![image](https://screensaver01.zap-hosting.com/index.php/s/AgSL8QcynHSfXFA/preview)



Afterwards the web client of the VNC console will open. Here you have the possibility to view the information that the server provides for the current time. This can for example be the startup process, login screen or the GUI of the operating system.

The following example shows a Windows VPS / Root server. This server has been successfully booted, so the VNC console shows the login screen at this state. You can log in here as well, even if the server has no active internet connection. Click on the "Send CtrlAltDel" button and log in with your username and password.



![image](https://screensaver01.zap-hosting.com/index.php/s/XTFS35AJBJaS86r/preview)
