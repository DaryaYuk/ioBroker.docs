---
BADGE-NPM version: https://img.shields.io/npm/v/iobroker.youtube?style=flat-square
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.youtube?label=npm%20downloads&style=flat-square
BADGE-Snyk Vulnerabilities for npm package: https://img.shields.io/snyk/vulnerabilities/npm/iobroker.youtube?label=npm%20vulnerabilities&style=flat-square
BADGE-node-lts: https://img.shields.io/node/v-lts/iobroker.youtube?style=flat-square
BADGE-Libraries.io dependency status for latest release: https://img.shields.io/librariesio/release/npm/iobroker.youtube?label=npm%20dependencies&style=flat-square
BADGE-GitHub: https://img.shields.io/github/license/klein0r/iobroker.youtube?style=flat-square
BADGE-GitHub repo size: https://img.shields.io/github/repo-size/klein0r/iobroker.youtube?logo=github&style=flat-square
BADGE-GitHub commit activity: https://img.shields.io/github/commit-activity/m/klein0r/iobroker.youtube?logo=github&style=flat-square
BADGE-GitHub last commit: https://img.shields.io/github/last-commit/klein0r/iobroker.youtube?logo=github&style=flat-square
BADGE-GitHub issues: https://img.shields.io/github/issues/klein0r/iobroker.youtube?logo=github&style=flat-square
BADGE-GitHub Workflow Status: https://img.shields.io/github/actions/workflow/status/klein0r/iobroker.youtube/test-and-release.yml?branch=master&logo=github&style=flat-square
BADGE-Snyk Vulnerabilities for GitHub Repo: https://img.shields.io/snyk/vulnerabilities/github/klein0r/iobroker.youtube?label=repo%20vulnerabilities&logo=github&style=flat-square
BADGE-Beta: https://img.shields.io/npm/v/iobroker.youtube.svg?color=red&label=beta
BADGE-Stable: http://iobroker.live/badges/youtube-stable.svg
BADGE-Installed: http://iobroker.live/badges/youtube-installed.svg
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.youtube/README.md
title: ioBroker.youtube
hash: /lng91j3s8SZ+6L0FGom2NvYFQYTJ552ZWGGwvtHJhI=
---
![标识](../../../en/admin/youtube.png)

# IoBroker.youtube
＃＃ 要求
-nodejs 14.5（或更高版本）
- js-controller 4.0.15（或更高版本）
- 管理适配器 6.0.0（或更高版本）

＃＃ 配置
要获取 API 密钥，您必须转至 [console.developers.google.com](https://console.developers.google.com/apis/dashboard)。

1. 创建一个新项目
2. 创建新的API密钥
3.添加库的“YouTube Data API v3”
4. 在实例配置中使用该 API-Key
5. 使用 id 和自定义名称在频道选项卡中添加多个频道

## 将所有统计数据记录到 InfluxDB
```javascript
on({ id: 'youtube.0.summary.json', change: 'any' }, async (obj) => {
    try {
        const youtubeJson = obj.state.val;
        const channels = JSON.parse(youtubeJson);
        const ts = Date.now();

        for (const channel of channels) {
            const alias = channel.customUrl.substr(1); // remove leading @

            await this.sendToAsync('influxdb.0', 'storeState', {
                id: `youtube.0.channels.${alias}.subscribers`,
                state: {
                    ts,
                    val: channel.subscriberCount,
                    ack: true,
                    from: `system.adapter.javascript.0.${scriptName}`,
                }
            });

            await this.sendToAsync('influxdb.0', 'storeState', {
                id: `youtube.0.channels.${alias}.views`,
                state: {
                    ts,
                    val: channel.viewCount,
                    ack: true,
                    from: `system.adapter.javascript.0.${scriptName}`,
                }
            });
        }
    } catch (err) {
        console.error(err);
    }
});
```

## Changelog

<!--
  Placeholder for the next version (at the beginning of the line):
  ### **WORK IN PROGRESS**
-->
### 4.3.0 (2023-08-28)

* (klein0r) Added customUrl to JSON summary

### 4.2.1 (2023-03-13)

* (klein0r) Video data as JSON

### 4.2.0 (2023-02-03)

* (klein0r) Allow alias or custom url in configuration
* (klein0r) Added request success indicators
* (klein0r) Added Ukrainian language

### 4.1.0 (2022-11-10)

NodeJS >= 14.5 is required

* (klein0r) Fixed issue with unescaped characters in URL (e.g. API key)
* (klein0r) Dropped Admin 5 support
* (klein0r) Added Ukrainian language

### 4.0.0 (2022-05-29)

NodeJS 14.x is required (NodeJS 12.x is EOL)

* (klein0r) Fixed last update time

## License

The MIT License (MIT)

Copyright (c) 2023 Matthias Kleine <info@haus-automatisierung.com>

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