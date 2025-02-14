---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.puppeteer/README.md
title: ioBroker.puppeteer
hash: ZnCM+j2vcSykqibFuRmMp4P4/WEy44jI65uogH0Ac2g=
---
![Logo](../../../en/adapterref/iobroker.puppeteer/admin/puppeteer.png)

![NPM-Version](https://img.shields.io/npm/v/iobroker.puppeteer.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.puppeteer.svg)
![Anzahl der Installationen](https://iobroker.live/badges/puppeteer-installed.svg)
![Aktuelle Version im stabilen Repository](https://iobroker.live/badges/puppeteer-stable.svg)
![NPM](https://nodei.co/npm/iobroker.puppeteer.png?downloads=true)

# IoBroker.puppenspieler
**Tests:** ![Testen und freigeben](https://github.com/foxriver76/ioBroker.puppeteer/workflows/Test%20and%20Release/badge.svg)

## Puppenspieler-Adapter für ioBroker
Headless-Browser zum Generieren von Screenshots auf Basis von Chrome

## Haftungsausschluss
Puppeteer ist ein Produkt von Google Inc. Die Entwickler dieses Moduls werden in keiner Weise von Google Inc. oder verbundenen Tochterunternehmen, Logos oder Marken unterstützt oder sind mit ihnen verbunden.

## Wie man
Der Adapter ist vollständig über Status konfigurierbar und bietet keine Einstellungen in der Admin-Oberfläche.
Die Zustände (außer `url`) bekommen kein ack-Flag vom Adapter und ack-Flags werden generell ignoriert.

### Zustände
#### Dateiname
Geben Sie den Dateinamen (vollständiger Pfad) des Bildes an.

#### URL
Geben Sie die URL an, von der Sie einen Screenshot machen möchten. Wird der Zustand geschrieben, wird sofort ein Screenshot erstellt.
Nachdem der Screenshot erstellt wurde, setzt der Adapter das ack-Flag des URL-Status auf „true“.

#### Volle Seite
Wenn dieser Status als wahr ausgewertet wird, wird ein Screenshot der gesamten Seite erstellt. Die Zuschneideoptionen werden ignoriert.

#### ZuschneidenLinks/Oben/Höhe/Breite
Konfigurieren Sie die Zuschneideoptionen in `px`, um nur den gewünschten Abschnitt der Seite zu scannen.
Wenn `fullPage` auf true gesetzt ist, wird kein Cropping durchgeführt.

#### WaitForSelector
Der Screenshot wird gemacht, nachdem der Selektor auf der Seite sichtbar ist, z. `#time`. Wenn `waitForSelector` aktiv ist, werden andere Warteoperationen wie `renderTime` ignoriert.

#### Renderzeit
Intervall in ms, das gewartet wird, bis die Seite gerendert wird

### Mitteilungen
Alternativ können Sie Screenshots erstellen, indem Sie Nachrichten an den Adapter senden.
Alle Optionen außer `url` und `ioBrokerOptions` werden direkt an die Puppeteer-API übergeben, die derzeit unterstützten Parameter finden Sie unten, für eine aktuellere Version überprüfen Sie die [API-Beschreibung](https://pptr.dev/api/puppeteer.screenshotoptions).
Zusätzlich können Sie einen `waitOption` definieren, um auf eine bestimmte Zeit oder auf einen Selektor zu warten. Schließlich können Sie mit der Option `ioBrokerOptions.storagePath` Screenshots direkt im ioBroker-Speicher unter `0_userdata.0` speichern, die dann über Admin- und Visualisierungsadapter angezeigt werden können.

```typescript
sendTo('puppeteer.0', 'screenshot', { url: 'https://www.google.com',
      ioBrokerOptions?: {
        /**
         * Define a filename for the ioBroker storage e.g. test.png
         */
        storagePath: string;
      },
      /**
       * Define at most one wait option
       * You can also look for other waitOptions currently supported by Puppeteer API
       * see e.g. https://puppeteer.github.io/puppeteer/docs/puppeteer.page.waitforfilechooser
       */
      waitOption?: {
        /**
         * Define a Timeout in ms
         */
        waitForTimeout?: 5000,

        /**
         * Wait for a given id/tag/etc to be occured
         */
        waitForSelector?: '#testId'
      },
      /**
       * Optionally, specify the viewport manually, see https://pptr.dev/api/puppeteer.viewport
       */
      viewportOptions?: {
        width: 800,
        height: 600
      },
      /**
       * The file path to save the image to. The screenshot type will be inferred
       * from file extension. If path is a relative path, then it is resolved
       * relative to current working directory. If no path is provided, the image
       * won't be saved to the disk.
       */
      path?: string,
      /**
       * When true, takes a screenshot of the full page.
       * @defaultValue false
       */
      fullPage?: boolean,
      /**
       * An object which specifies the clipping region of the page.
       */
      clip?: {
        x: number,
        y: number,
        width: number,
        height: number
      };
      /**
       * Quality of the image, between 0-100. Not applicable to `png` images.
       */
      quality?: number,
      /**
       * Hides default white background and allows capturing screenshots with transparency.
       * @defaultValue false
       */
      omitBackground?: boolean,
      /**
       * Encoding of the image.
       * @defaultValue 'binary'
       */
      encoding?: 'base64' | 'binary',
      /**
       * If you need a screenshot bigger than the Viewport
       * @defaultValue true
       */
      captureBeyondViewport?: boolean,
  }, obj => {
      if (obj.error) {
        log(`Error taking screenshot: ${obj.error.message}`, 'error');
      } else {
        // the binary representation of the image is contained in `obj.result`
        log(`Sucessfully took screenshot: ${obj.result}`);
      }
});
```

## Changelog
<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->
### 0.2.6 (2022-08-14)
* (foxriver76) we now close the page also when screenshot taken via message

### 0.2.5 (2022-08-14)
* (foxriver76) we have optimized the viewport option

### 0.2.4 (2022-08-12)
* (foxriver76) allow settings viewport options
* (foxriver76) the default viewport is now the max resolution

### 0.2.3 (2022-08-12)
* (foxriver76) optimized path check for relative paths

### 0.2.1 (2022-06-09)
* (foxriver76) we now install required shared libraries on adapter installation on linux

### 0.2.0 (2022-05-20)
* (foxriver76) added option to save files to the ioBroker storage via messages by using `ioBrokerOptions.storagePath` (closes #2)

### 0.1.0 (2022-05-16)
* (foxriver76) initial release

## License
MIT License

Copyright (c) 2022 Moritz Heusinger <moritz.heusinger@gmail.com>

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