---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.intex/README.md
title: ioBroker.intex
hash: NwQnuxNpFXZ5n4vtiRTbKM9JfyAWEb1zWbSw14lLVDU=
---
![Логотип](../../../en/adapterref/iobroker.intex/admin/intex.png)

![НПМ-версия](https://img.shields.io/npm/v/iobroker.intex.svg)
![Загрузки](https://img.shields.io/npm/dm/iobroker.intex.svg)
![Количество установок](https://iobroker.live/badges/intex-installed.svg)
![Текущая версия в стабильном репозитории.](https://iobroker.live/badges/intex-stable.svg)
![НПМ](https://nodei.co/npm/iobroker.intex.png?downloads=true)

# IoBroker.intex
**Тесты:** ![Тестирование и выпуск](https://github.com/TA2k/ioBroker.intex/workflows/Test%20and%20Release/badge.svg)

## Адаптер intex для ioBroker
Адаптер для Intex Whirlpool с модулем Wi-Fi

## Стратегия взаимодействия с пулом и облаком
### Об облаках
#### Облако вторичное; Локальный пул, если доступен
В этом режиме система пытается подать команду управления и команду обновления локально. При возникновении ошибки в локальной связи система переключается на работу в облаке до повторного запуска адаптера.

IP-адрес и порт берутся из облака. Если IP-адрес тот же, пул необходимо заново зарегистрировать в приложении. Нажмите и удерживайте кнопку подключения и выполните поиск в пуле. Удаление его из приложения обычно не требуется.

#### Облако вторичное; Бассейн только местный
В этом режиме система выдает команду управления и команду обновления локально. При возникновении ошибки в локальной связи система не переключается на работу в облаке.

Здесь можно установить интервал 0,5 минуты.

IP-адрес и порт берутся из облака. Если IP-адрес тот же, пул необходимо заново зарегистрировать в приложении. Нажмите и удерживайте кнопку подключения и выполните поиск в пуле. Удаление его из приложения обычно не требуется.

#### Только облако
В этом режиме система отправляет только команду управления и команду обновления через облако.

##### Авторизоваться
Введите почту и пароль приложения Intex.

### Местный
#### Только локально
В локальном режиме в настоящее время также предлагаются функции, которые пул не поддерживает. В разделе «Адрес» необходимо указать либо DNS-имя пула на маршрутизаторе, либо IP-адрес пула.

Здесь также можно установить интервал 0,5 минуты.

IP-адрес пула можно найти с помощью кнопки поиска. Однако маршрутизаторы могут предотвратить это, если, например. Б. Устройствам WLAN не разрешено взаимодействовать друг с другом, либо порты или встроенная трансляция заблокированы в локальном брандмауэре компьютера.

## Управление функциями спа
Для параметра «intex.0.-id-.control.-command-», установленного в значение true или false, контролируется состояние команды пула.

## Обсуждение и вопросы на немецком языке
https://forum.iobroker.net/topic/47932/test-intext-app-v0-0-x

## Changelog

### 0.1.5

* (PLCHome) spelling mistake sanitzer to sanitizer on status control.sanitizer and control.sanitizerTime corrected.

### 0.1.4

* (PLCHome) Changing read-only objects, e.g. temperature, no longer causes a crash.

### 0.1.3

* (PLCHome) The remaining time for the filter is corrected to the disinfection time if it is longer

### 0.1.2

* (PLCHome) Fixed filter remaining time on heating from 1 to -1 for infinity

### 0.1.1

* (PLCHome) Remaining time for filter and sanitizer added under control.
* (PLCHome) Refresh added under Control.
* (PLCHome) Remote deleted because Control can do it better.

### 0.1.0
* (rbartl/PLCHome) Support local IP. Both via cloud and only locally without cloud. Thanks to Austria to Robert Bartl.
* (PLCHome) Confirm directly after switching via Control.

### 0.0.7
* (PLCHome) Switching via remote works again.
* (PLCHome) After switching via Control, the previous traffic status can be transmitted from the cloud. This can lead to a toggling of the status.

### 0.0.6
* (PLCHome) Defined setting of states
* (PLCHome) Change Fahrenheit Celsius
* (PLCHome) "control.temperature", read only, object from 0.0.5 must be deleted once.

### 0.0.5
* (PLCHome) Set temperature added, object must be deleted once.
* (PLCHome) Decoding of status information

### 0.0.1
* (TA2k) initial release

## License
MIT License

Copyright (c) 2021 - 2023 TA2k <tombox2020@gmail.com>

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