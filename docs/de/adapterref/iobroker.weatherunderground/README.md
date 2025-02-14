---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.weatherunderground/README.md
title: ioBroker.weatherunderground
hash: a5jiLETlcvxJgIyxlf4MfTQHi/MKIdodXzc3k7GgYcw=
---
![Logo](../../../en/adapterref/iobroker.weatherunderground/admin/wu.png)

![Anzahl der Installationen](http://iobroker.live/badges/weatherunderground-stable.svg)
![NPM-Version](http://img.shields.io/npm/v/iobroker.weatherunderground.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.weatherunderground.svg)

# IoBroker.weatherunderground
![Test und Freigabe](https://github.com/iobroker-community-adapters/iobroker.weatherunderground/workflows/Test%20and%20Release/badge.svg) [![Übersetzungsstatus](https://weblate.iobroker.net/widgets/adapters/-/weatherunderground/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

**Dieser Adapter verwendet Sentry-Bibliotheken, um Ausnahmen und Codefehler automatisch an die Entwickler zu melden.** Weitere Details und Informationen zum Deaktivieren der Fehlerberichterstattung finden Sie unter [Sentry-Plugin-Dokumentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry Reporting wird ab js-controller 3.0 verwendet.

ioBroker-Adapter zum Laden der 24-Stunden-Wettervorhersage für Ihren Standort aus [Das Wetter unter der Erde](http://www.wunderground.com/).
Der Adapter lädt alle 15-minütigen (Standard) täglichen und stündlichen Prognosedaten.

## Anmerkungen
Sie können diesen Adapter mit der Bereitstellung eines offiziellen API-Schlüssels „PWS-Besitzer“ verwenden oder den API-Schlüssel leer lassen, um Schlüssel zu verwenden, die aus der WU-Webseite extrahiert wurden.

## Symbolsätze
Bei Verwendung der „Legacy API“ stehen verschiedene Symbolsätze zur Verfügung, siehe unten. Für die Nutzung mit der neuen API haben sich die Bildnamen geändert (siehe https://docs.google.com/document/d/1dNCf6nF6cjm4oOxQxjtqNuAvG_iEe5f9MQH1xlCeV4s/edit) und basieren jetzt auf Zahlen ... sie können z. B. von heruntergeladen werden https://drive.google.com/drive/folders/0B6fWQWXuE09OOWtBOXJNX190TDQ und kann als benutzerdefiniertes Set verwendet werden (siehe unten).

Ändern Sie in den Adaptereinstellungen „Custom Icon-Base-URL“ in einen der verfügbaren Icon-Sets auf Weatherunderground: (Quelle: https://www.wunderground.com/weather/api/d/docs?d=resources/icon-sets )

| Icon-Set | URL | Beispiel |
| ------------- | -------------------------------- | --------------------- 	|
| 1 | https://www.wunderground.com/static/i/c/a/ | ![Alt-Text](https://www.wunderground.com/static/i/c/a/partlycloudy.gif) |
| 3 | https://www.wunderground.com/static/i/c/c/ | ![Alt-Text](https://www.wunderground.com/static/i/c/c/partlycloudy.gif) |
| 4 | https://www.wunderground.com/static/i/c/d/ | ![Alt-Text](https://www.wunderground.com/static/i/c/d/partlycloudy.gif) |
| 5 | https://www.wunderground.com/static/i/c/e/ | ![Alt-Text](https://www.wunderground.com/static/i/c/e/partlycloudy.gif) |
| 6 | https://www.wunderground.com/static/i/c/f/ | ![Alt-Text](https://www.wunderground.com/static/i/c/f/partlycloudy.gif) |
| 7 | https://www.wunderground.com/static/i/c/g/ | ![Alt-Text](https://www.wunderground.com/static/i/c/g/partlycloudy.gif) |
| 8 | https://www.wunderground.com/static/i/c/h/ | ![Alt-Text](https://www.wunderground.com/static/i/c/h/partlycloudy.gif) |
| 9 | https://www.wunderground.com/static/i/c/i/ | ![Alt-Text](https://www.wunderground.com/static/i/c/i/partlycloudy.gif) |
| 10 | https://www.wunderground.com/static/i/c/j/ | ![Alt-Text](https://www.wunderground.com/static/i/c/j/partlycloudy.gif) |
| 11 | https://www.wunderground.com/static/i/c/k/ | ![Alt-Text](https://www.wunderground.com/static/i/c/k/partlycloudy.gif) |
| 11 | https://www.wunderground.com/static/i/c/k/ | ![alt text](https://www.wunderground.com/static/i/c/k/partlycloudy.gif) |

Oder Sie können auch Ihre eigenen „benutzerdefinierten“ Symbole verwenden. Zu diesem Zweck müssen die folgenden GIF-Dateien in einem Basis-URL-Verzeichnis bereitgestellt werden:

| Symbol für Tag | Symbol für Nacht |
| -----------------------------	| ----------------------------- |
| chanceflurries.gif | nt_chanceflurries.gif |
| chancerain.gif | nt_chancerain.gif |
| chancesleet.gif | nt_chancesleet.gif |
| chancesleet.gif | nt_chancesleet.gif |
| chancesnow.gif | nt_chancesnow.gif |
| chancetstorms.gif | nt_chancetstorms.gif |
| chancetstorms.gif | nt_chancetstorms.gif |
| klar.gif | nt_clear.gif |
| wolkig.gif | nt_cloudy.gif |
| flurries.gif | nt_flurries.gif |
| nebel.gif | nt_fog.gif |
| dunstig.gif | nt_hazy.gif |
| mostcloudy.gif | nt_mostlycloudy.gif |
| mostsunny.gif | nt_mostlysunny.gif |
| teilweise bewölkt.gif | nt_partlycloudy.gif |
| teilweise sonnig.gif | nt_partlysunny.gif |
| Schneeregen.gif | nt_sleet.gif |
| regen.gif | nt_rain.gif |
| Schneeregen.gif | nt_sleet.gif |
| teilweise bewölkt.gif | nt_partlycloudy.gif |
| sunny.gif | nt_sunny.gif |
| tstorms.gif | nt_tstorms.gif |
| wolkig.gif | nt_cloudy.gif |

## Im ioBroker Forum (Deutsch)
http://forum.iobroker.org/viewtopic.php?f=20&t=2042&sid=a863d19838bc49439759bef89fcad1c3

## Machen
Es gibt immer noch ein Problem mit der Kodierung. Die Adressen mit „äüöß“ werden falsch angezeigt.

## Changelog
<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->
### 3.6.0 (2023-09-09)
* (mcm1957) Icon urls at admin ui have been adapted to weatherunderground website changes (#158)
* (mcm1957) Forecast periods have been extended

### 3.5.0 (2023-09-08)
* (mcm1957) Adapter now requires node 16 or newer
* (mcm1957) Dependencies have been updated
* (waldmensch1) Cloudcover states have been added (PR #178)
* (mcm1957) Date format has been fixed to avoid incorrect display with newer admin versions (#191)
* (mcm1957) Forecast urls have been adapted to weatherunderground website changes (#158)

### 3.4.3 (2023-08-15)
* (Aplollon77) Translations have been updated (#159)
* (mcm1957) The testenvironment has been updated to use node 16/18/20
* (bluefox) Dependencies have been updated

### 3.4.2 (2022-04-26)
* (Apollon77) Added special logging when no current observation data are available because Station most likely offline to reduce confusion

### 3.4.1 (2022-03-13)
* (bluefox) Use axios for communication
* (bluefox) make sure date states are filled correctly

### 3.4.0 (2022-03-10)
* (Apollon77) If no official API-Key is used: Move schedule if default is used to better spread the requests over time to prevent peaks; Additionally add a random delay in the start minute
* (Apollon77) Further optimizations and additional logging

### 3.3.1 (2021-06-28)
* (Apollon77) Optimize for js-controller 3.3

### 3.3.0 (2021-01-22)
* (Apollon77) Optimize for js-controller 3.2
* (Apollon77) js-controller 2.0 is now required at least

### 3.2.5 (2020-12-27)
* (Apollon77) Prevent crash case (Sentry IOBROKER-WEATHERUNDERGROUND-1, IOBROKER-WEATHERUNDERGROUND-2)

### 3.2.3 (2020-12-26)
* (Apollon77) make sure adapter do not crash when no data could be read
* (Apollon77) Add Sentry error reporting

### 3.2.2 (2020-12-02)
* (Apollon77) icons sometimes did not have a correct extension
* (Apollon77) Correct some cases with different types of locations when reading data

### 3.2.1
* (raintonr) Corrected 'Imperial' terminology.

### 3.2.0 (2019-12-28)
* (StrathCole) fix forecast expiry time
* (StrathCole) add visibility index to objects on hourly forecast

### 3.1.6 (2019-10-16)
* (Bjoern3003) adjust to WU changes, now v3 API for hourly data
* (Apollon77) run once after installation/update

### 3.1.3
* (Apollon77) text correction

### 3.1.2 (2019-07-27)
* (Apollon77) use new parameters to get decimal precision values

### 3.1.1 (2019-07-14)
* (Apollon77) add windDirection as string calculated based on degrees

### 3.1.0 (2019-07-12)
* (Apollon77) remove option for legacy API because disabled by WU

### 3.0.14 (2019-07-11)
* (Apollon77) optimize checking of pws station id

### 3.0.13 (2019-07-10)
* (Apollon77) Fix error in image url handling

### 3.0.11/12 (2019-07-09)
* (Apollon77) Re-Fetch PWS station key on Error 401

### 3.0.10 (2019-05-27)
* (Apollon77) Adopt logic to WU changes

### 3.0.8 (2019-03-23)
* (Apollon77) Add additional guidance when location is not found by WU

### 3.0.7 (2019-03-22)
* (Apollon77) implement to extract used "legacy" API keys out of WU website to allow restore of functionality for now
* (Apollon77) Also extract API keys for newer API version from website to be usable together with real "PWS owner keys" in future
* (Apollon77) optionally get data using the New APIs (as well as the officially available PWS-Owner APIs as also additional ones to restore functionality)
* (Apollon77) Admin 2 support removed and adapted the Admin 3 texts as needed for now

### 2.0.4 (2018-08-19)
* (René) some typos
* (bluefox) Write only numbers and not strings

### 2.0.3 (2018-07-30)
* (bluefox) Warning! Breaking changes! States are renamed.
* (bluefox) Refactoring of states and roles

### 1.1.2 (2017-11-24)
* (Apollon77) Add option to specify image format for custom image urls

### 1.1.1 (2017-11-08)
* (Apollon77) Optimize API usage by getting all data with one call instead of two
* (Apollon77) Add support for multiple API-Keys

### 1.1.0 (2017-10-30)
* (Apollon77) Add option to overwrite Icon Base URL

### 1.0.8 (2017-07-12)
* (DeepCoreSystem) add 2 current observation values, fixes of some datapoint caps.

### 1.0.7 (2017-06-19)
* (Dutchman) add Dutch language suppport

### 1.0.6 (2017-05-16)
* (Rene) bug fixing
	+ all 4 sets are enabled as default
	+ change of checkbox enables saves button

### 1.0.5 (2017-05-14)
* (Rene) hourly forecast extend to 36h

### 1.0.4 (2017-04-09)
* (Rene) parse much more data
   + today's 24 h
   + next 4 days / nights as text
   + next 4 days
   + current values
   each can be enabled or disabled

### 1.0.3 (2016-11-01)
* (bluefox) Catch parse errors

### 1.0.2 (2016-10-29)
* (Apollon77) make sure precip values are always integers

### 1.0.1 (2016-07-21)
* (jens-maus) conversion from feet to meter for observation_location

### 1.0.0 (2016-07-12)
* (Apollon77) add daily rain level forecast

### 0.2.0 (2016-07-01)
* (Apollon77) Add Error handling and station-usage for forcasts

### 0.1.1 (2016-06-07)
* (ploebb) Fix forecast api URL

### 0.1.0 (2016-05-07)
* (bluefox) convert text to floats
* (bluefox) support languages

### 0.0.5
corrected humidity value within current weather info (slice + unit)

### 0.0.4
checking for spaces in location
added current conditions

### 0.0.3
bugfix in summed pop-value.

### 0.0.2
config dialog fixed

### 0.0.1
initial release with all basics to load WU-forecast data

## License

The MIT License (MIT)

Copyright (c) 2015-2023 dschaedl <daniel.schaedler@gmail.com>, iobroker-community-adapters

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