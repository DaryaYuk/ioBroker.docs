---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.pushbullet/README.md
title: Адаптер pushbullet ioBroker
hash: CtKKZqxl/lmSpVf4JdH+/LeT9EhUHhmLI5c+DX5vhTk=
---
![Логотип](../../../en/adapterref/iobroker.pushbullet/admin/pushbullet.png)

![Количество установок](http://iobroker.live/badges/pushbullet-stable.svg)

# Адаптер ioBroker pushbullet
Отправляйте pushbullet-уведомления от ioBroker.

## Использование
Чтобы отправить уведомление от ScriptEngine, просто напишите:

```javascript
// send note
sendTo("pushbullet", "message body");

//OR

sendTo("pushbullet", {
    message: "message body",    //The Message you want to send
    title: "title",             //The Title of your message
    type: "note"                //Type Note
});

// send link
sendTo("pushbullet", {
    link: "http://www.example.com", //The Link you want to send
    title: "Title",             //The Title of your link
    type: "link"                //Type link
});

// send file

sendTo("pushbullet", {
    file: "/path/to/file",  //The file you want to send
    title: "Title",         //The Title of your file
    type: "file"            //Type file
});
```

<!-- Заполнитель следующей версии (в начале строки):

### **РАБОТА В ПРОГРЕССЕ** -->

## Changelog
### 1.0.1 (2023-09-10)
* (bluefox) Breaking change: Only node version 16+ supported
* (bluefox) Added JSON config and used the latest version of a pushbullet library
* (bluefox) Added encryption

### 0.1.0 (2021-10-15)
* (bluefox) Refactoring

### 0.0.11 (2015-10-11)
* (Jens1809) Man kann nun Pushnachrichten an bestimmte Geräte schicken indem man die GeräteID mit angibt.
* sendTo("pushbullet", {
  message: "message body",    //The Message you want to send
  title: "title",             //The Title of your message
  type: "note",                //Type Note
  receiver: "ID hier einsetzen" //GeräteID
  });

### 0.0.8 (2015-09-26)
* (Jens1809) Adapter empfängt nun Push Nachrichten und schreibt die Daten der Nachricht in die Objekte:
* - pushbullet.0.push.type
- pushbullet.0.push.title
- pushbullet.0.push.message
- pushbullet.0.push.payload

### 0.0.7 (2015-09-24)
* (Jens1809) Möglichkeit an ausgewählte Geräte zu senden ohne an den kompletten Account zu senden.

### 0.0.6 (2015-07-25)
* (Jens1809) Publish on NPM

## License

The MIT License (MIT)

Copyright (c) 2015-2023 Jens1809

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