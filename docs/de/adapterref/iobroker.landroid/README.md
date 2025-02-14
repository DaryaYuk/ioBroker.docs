---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.landroid/README.md
title: Dieser Adapter ist veraltet und wird nicht weiterentwickelt
hash: 0EHhr5qlOIy7tWNtiOKpY5u9grZDQwwP6h6mvcA9Q3Q=
---
![Logo](../../../en/adapterref/iobroker.landroid/admin/landroid.png)

![Anzahl der Installationen](http://iobroker.live/badges/landroid-stable.svg)
![NPM-Version](http://img.shields.io/npm/v/iobroker.landroid.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.landroid.svg)
![Abhängigkeitsstatus](https://img.shields.io/david/iobroker-community-adapters/iobroker.landroid.svg)
![Bekannte Schwachstellen](https://snyk.io/test/github/iobroker-community-adapters/ioBroker.landroid/badge.svg)
![NPM](https://nodei.co/npm/iobroker.landroid.png?downloads=true)
![Travis-CI](http://img.shields.io/travis/iobroker-community-adapters/ioBroker.landroid/master.svg)
![AppVeyor](https://ci.appveyor.com/api/projects/status/github/iobroker-community-adapters/ioBroker.landroid?branch=master&svg=true)
![Greenkeeper-Abzeichen](https://badges.greenkeeper.io/iobroker-community-adapters/ioBroker.landroid.svg)

# Dieser Adapter ist veraltet und wird nicht weiterentwickelt
-----

Derzeit ist keine Weiterentwicklung dieses Adapters geplant. __Bitte migrieren Sie zum ioBroker.worx-Adapter__, der beibehalten wird.
Wenn Sie Funktionen bei ioBroker.worx vermissen, öffnen Sie ein Problem in diesem Repository (https://github.com/tp1de/ioBroker.worx/issues).

ioBroker.landroid wird noch einige Zeit verfügbar bleiben, aber bedenken Sie, dass es nicht an Node 20 und den kommenden js-controller v5 angepasst wird.

-----

# IoBroker.landroid
## Ein Worx Landroid-Adapter für ioBroker
Dies ist ein ioBroker-Adapter für Ihre Worx Landroid-Mähmaschine. Es wurde mit einem Landroid WG796E getestet.

## Changelog

<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->
### **WORK IN PROGRESS**
-   (mcm1957) changed: Testing has been changed to support node 16, 18 and 20
-   (mcm1957) changed: Dependencies have been updated

### 1.0.3
* (ldittmar) compact mode compatibility added
* (ldittmar) add chinese support

### 1.0.2
* (ldittmar) Support of admin3

### 1.0.0
* (ldittmar) Fixed little changes

### 0.1.1
* (ldittmar) Change PIN field to type password

### 0.1.0
* (ChrBender) Bug with start/stop button fixed

### 0.0.4
* (ldittmar) Bugfixes

### 0.0.3
* (ldittmar) Minor bug fixes / compatibility with the WG797E.1 mower

### 0.0.2
* (ldittmar) read all important informations (can't start or stop ist at this time)

### 0.0.1
* (ldittmar) initial commit

## License
The MIT License (MIT)

Copyright (c) 2018-2019 ldittmar <iobroker@lmdsoft.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.