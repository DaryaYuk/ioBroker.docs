---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.firetv/README.md
title: kein Titel
hash: fjWzek3jOInDjaIinISqARTUz5CM+4h3/ctYyQQkH2k=
---
![Logo](../../../en/adapterref/iobroker.firetv/admin/firetv.png)

![Anzahl der Installationen](http://iobroker.live/badges/firetv-community-installed.svg)
![Stabile Version](http://iobroker.live/badges/firetv-community-stable.svg)
![NPM-Version](https://img.shields.io/npm/v/iobroker.firetv.svg)
![Tests](https://img.shields.io/travis/soef/iobroker.firetv/master.svg)
![Lizenz](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)
![Build-Status](https://secure.travis-ci.org/soef/iobroker.firetv.svg?branch=master)

### IoBroker.firetv
<!--
[![NPM-Version](https://badge.fury.io/js/iobroker.firetv.svg)](https://www.npmjs.com/package/iobroker.firetv)
-->

Mit diesem Adapter können Sie einige Funktionen Ihres Fire TV oder Fire TV Sticks steuern.
Z.B.:

- An aus
- Senden Sie wichtige Ereignisse
- Senden Sie Textzeichenfolgen an Eingabefelder
- Apps starten/stoppen
- Neustart
- Shell-Befehle ausführen

#### Einige Infos
Dieser Adapter nutzt Funktionen der „Android Debug Bridge“, bekannt als „adb“. Adb ist Teil des Android Developer SDK. Da Fire TV über ein Android-Betriebssystem verfügt, kann es über ADB gesteuert werden.

#### Anforderungen
Um diesen Adapter nutzen zu können, müssen Sie mindestens das ADB-Paket des Android SDK installieren. Um nicht das komplette Android SDK zu installieren, sollten Sie *Minimal ADB und Fastboot* installieren.

Suchen Sie auf Google (Minimal ADB und Fastboot) nach dem neuesten Download-Link.

Alternativ können Sie *adbLink* verwenden.

<!--

### **ARBEIT IN ARBEIT** -->

## Changelog
### 2.0.2 (2023-09-09) 
* (jonaskn) A crash has been fixed (#56)

### 2.0.1 (2023-09-07)
* (Grothesk242) make compatible with Node.js 18+
* (bluefox) a minimum node.js version is 16

### 1.0.0 (2020-04-09)
* (foxriver76) compatibility for js-c 3

## License
The MIT License (MIT)

Copyright (c) 2016-2023 soef <soef@gmx.net> and Community developers

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