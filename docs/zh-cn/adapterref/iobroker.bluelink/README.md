---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.bluelink/README.md
title: ioBroker.bluelink
hash: z1l3H2dlLAIhSJIMG6J5WNO9qS8qfxuqGoU26EL9HNg=
---
![标识](../../../en/adapterref/iobroker.bluelink/admin/bluelink.png)

![NPM版本](https://img.shields.io/npm/v/iobroker.bluelink.svg)
![下载](https://img.shields.io/npm/dm/iobroker.bluelink.svg)
![安装数量（最新）](https://iobroker.live/badges/bluelink-installed.svg)
![安装数量（稳定）](https://iobroker.live/badges/bluelink-stable.svg)
![国家公共管理](https://nodei.co/npm/iobroker.bluelink.png?downloads=true)

# IoBroker.bluelink
![测试与发布](https://github.com/Newan/iobroker.bluelink/workflows/Test%20and%20Release/badge.svg) [![翻译状态](https://weblate.iobroker.net/widgets/adapters/-/bluelink/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

## IoBroker 的 bluelink 适配器
用于控制现代或起亚车辆的适配器

讨论：https://forum.iobroker.net/topic/43592/adapter-hyundai-bluelink-oder-kia-uvo

登录信息：https://developers.kia.com/web/v1/kia/specification/account/account_authorize

<!-- 下一个版本的占位符（在行的开头）：

https://github.com/AlCalzone/release-script#usage npm run 发行版主要 -- -p iobroker 许可证 --all 0.9.8 -> 1.0.0 npm run 发行版次要 -- -p iobroker 许可证 --all 0.9 .8 -> 0.10.0 npm run 发布补丁 -- -p iobroker 许可证 --all 0.9.8 -> 0.9.9 npm run 发布预发布 beta -- -p iobroker 许可证 --all v0.2.1 -> v0.2.2 -beta.0

### **正在进行中** -->
## 捐赠
[![](https://www.paypalobjects.com/de_DE/DE/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=L55UBQJKJEUJL)

## Changelog

### 2.3.5 
* (arteck) add force_login button
* (arteck) corr history bug

### 2.3.4 (2023-07-19)
* (arteck) clima control is redesigned

### 2.3.3 (2023-07-19)
* (arteck) charge_limit_fast and charge_limit_slow is now in control folder

### 2.3.2 (2023-04-12)
* (arteck) force update only selected vin
* (arteck) add buttons for force_refresh_from_server and force_refresh_from_car

### 2.3.1 (2023-04-10)
* (arteck) io-package update

### 2.3.0 (2023-04-10)
* (arteck) force update
* (stefan.cloer) force_update corr, lastInfoUpdate corr, typo corr
* (arteck) add batteryControlState12V init is 60
* (arteck) max requests set to 400
* (arteck) vin id for force_refresh 
* (arteck) positionURL

### 2.2.7 (2023-03-07)
* (arteck) fix / clima control
* (arteck) force update add to admin
* (devdev24) Fixed error causing dead on-board batteries
* (arteck) door status is correct

### 2.2.6 (2022-11-04)
* (arteck) fix / extend clima & errorcounter

### 2.2.3 (2022-04-06)
* (Newan) Update dependencies

### 2.2.0
* (Newan) Test release for 503 Error

### 2.2.0

* (TA2k, Newan) Adding refresh stop if 12V battery is under 50%.

### 2.1.2
* (TA2k, Newan) Update lib bluelinky

### 1.1.1
* (Newan) Bug fixes vehicle location

### 1.0.9
* (Newan) + (dklinger) Bug fixes

### 1.0.8
* (Newan)Add charge start/stop option

### 1.0.7
* (Newan)Fix for KIA Sorento (Diesel)

### 1.0.6
* (Newan) Fix for server connection

### 1.0.3
* (Newan) Changes for PHEV

### 1.0.2
* (Newan) New lib

### 1.0.0
* (Newan) First stable version

## License
MIT License

Copyright (c) 2022 Newan <info@newan.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.