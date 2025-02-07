# Wemos D1 Mini 4 Node Smart Control


## 📌 Table of Contents

- [About the Project](#-about-the-project)
- [Screenshots](#-screenshots)
- [Usage](#-usage)
- [Configuration for Tasmota](#%EF%B8%8F-configuration-for-tasmota))

---

## 📖 About the Project

This board is designed as a multi-purpose board which can help in using the standard Wemos D1 Mini board based on ESP8266 to a 4 relay smart control unit. 
The relays are miniature in size which can control upto 5A, 250AC (or 7A, based on which unit you used). It has 4 inputs which can be connected to AC switch and 4 outputs can be connected to loads. The board can be fitted behind the switchboard as an after market fit without rewiring, provided there is a neutral line available. 

Additional taping points are added for using the device in many other configurations. Due to limited inputs, there is also 3 digital switch support based on ADC divider circuit provisioned. 

## 🖼 Screenshots

![Top View - PCB](Pics/top0.png)
![Top View 1](Pics/top1.png)
![Top View 2](Pics/top2.png)

![Bottom View - PCB](Pics/bottom0.png)
![Bottom View 1](Pics/bottom1.png)

## 🚀 Usage
The design was done for using with Tasmota firmware, but user can use any firmware which can support the below configuraton.
- Inputs: D0, D1, D2, D3 and ADC (with voltage divider option for 3 digital pins)
- Outputs: D5, D5, D7 and D8

  Note: D3 has a pull-up and boot fails if pulled down during power on. 

D0 to D3 supports AC detection circuit. For using ADC divider based configuration, connect three switches between the marked joints (S1,S2,S3). All combinations of key presses and short circuits (SCB/SCG) are detectable via different ADC values if the default specified resistors are used. Other combinations could be used if only one or two switches are needed. 

Note: Refer BOM available under Gerber directory to see the component details.

## ⚙️ Configuration for Tasmota
Following configuration can be used for Tasmota firmware.

![Configuration for Tasmota devices](Pics/config.png)

For AC detection circuit, you can also use following additional commands in tasmota console:
- switchdebounce0 109 : To set AC detection with 100ms debounce time
- switchmode0 1 : If you want to follow the manual switch instead of toggle every time


## 📜 License

This project is licensed under the MIT License 
