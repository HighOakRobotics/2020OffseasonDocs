---
permalink: /wireless-setup
title: Wireless Code Updater Setup
---

* Go to File > Settings
* Go to Tools > External Tools
* Press the plus sign to add a new external tool.
* Enter the following into their corresponding blanks; leave everything else as is.
  * Name: Enable ADB over TCP/IP
  * Program: $ModuleSdkPath$/platform-tools/adb
  * Arguments: tcpip 5555
  * Working Directory: $ProjectFileDir$
* Press the plus sign to add another external tool.
* Enter the following into their corresponding blanks; leave everything else as is.
  * Name: Connect to ADB over WiFi Direct
  * Program: $ModuleSdkPath$/platform-tools/adb
  * Arguments: connect 192.168.43.1:5555
  * Replace the IP with 192.168.49.1:5555 if you’re not using a control hub
  * Working Directory: $ProjectFileDir$
