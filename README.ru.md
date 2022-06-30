# browserpedals


[![en](https://img.shields.io/badge/lang-en-blue.svg)](README.md)


Данная программа позволяет управлять просмотром любого видео/аудио в веб-браузере с использованием ножных педалей - приостановить/продолжить или вернуться назад - даже когда веб-браузер находится не в фокусе.

Это может быть полезно при транскрибировании - прослушивании видео в веб-браузере и одновременном наборе текста на клавиатуре - где ножные педали могут использоваться для периодической приостановки видео или возврата назад во времени.


## Требования:

- Python 3
- Веб-браузер Mozilla Firefox


## Установка:

В среде Linux, откройте командную строку и введите:
```
~> python3 -m pip install --no-cache-dir browserpedals
```

В среде Windows, откройте командную строку или Windows PowerShell и введите:
```
~> py -m pip install --no-cache-dir browserpedals
```


## Использование:

Подключите педали к USB-порту компьютера.

Запустите программу. Если программа была установлена с использованием PIP, как показано выше, тогда на рабочем столе и в меню приложений для нее был автоматически создан ярлык `BrowserPedals`. В этом случае программу можно запустить двойным кликом мыши на этом ярлыке, или кликнув правой кнопкой мыши на видео-файле или аудио-файле, который мы хотим открыть, и в выпадающем меню выбрав программу `BrowserPedals`.

Технически, программу `browserpedals.py` (а также отдельно подмодули `usepedals.py` (только тестирование педалей) и `detectpedals.py` (только распознавание педалей)) можно также запустить из командной строки как Python-скрипты:
```
~> python3 browserpedals.py
```

Программа использует веб-браузер в качестве пользовательского интерфейса.

Подождите, пока откроется новое окно браузера. На это может уйти до минуты.

В браузере откроется стартовая страница с информацией о программе.

Также, откроется диалоговое окно с пошаговыми инструкциями, где пользователю будет предложено протестировать педали, чтобы убедиться, что они работают, а если педали неизвестны, чтобы автоматически распознать их. Диалоговое окно закроется после того, как педали пройдут тест.

В окне браузера перейдите на любой веб-сайт, содержащий видео или аудио (или откройте локальный видео-файл или аудио-файл на компьютере: в браузере Firefox нажмите клавишу `Alt`, чтобы открыть меню браузера, и выберите `Файл--Открыть файл`. В браузерах Chrome или Edge нажмите клавишу `Ctrl+O`.)

### Как начать управлять видео/аудио при помощи педалей:

Чтобы начать управлять видео/аудио при помощи педалей, кликните мышью кнопку `Воспроизведение` на видео хотя бы один раз.

Чтобы прекратить управлять данным видео/аудио при помощи педалей, кликните мышью кнопку `Пауза` на видео (не педалями).
После этого вы сможете начать управлять любым другим видео на сайте, кликнув мышью на его кнопке `Воспроизведение`.

Иногда нужно подождать примерно минуту, пока программа начнет управлять выбранным видео, или кликнуть мышью кнопку `Воспроизведение` на видео несколько раз.

### Как управлять видео/аудио при помощи педалей:

Чтобы приостановить/продолжить просмотр видео, нажмите правую педаль (или другую назначенную вами педаль).

Чтобы отмотать видео назад, нажмите левую педаль (или другую назначенную вами педаль).


## Автоматическое распознавание педалей:

В настоящее время программа поддерживает только один конкретный вид педалей, с которыми она работает без дополнительной настройки - это ножные педали "Thrustmaster wheel" (Thrustmaster 360 SPIDER PC).

Если используются другие педали, программа попытается распознать их автоматически. Просто подключите педали к компьютеру, запустите программу и следуйте инструкциям на экране. Если педали будут удачно распознаны, информация будет сохранена в файле `auto_detected_pedals.txt`, и при следующем запуске программы новые педали будут распознаны автоматически.

Пользователи, использующие педали, успешно распознанные программой, могут отправить вышеуказанный файл разработчику, чтобы последующие версии программы работали с данными педалями без дополнительной настройки:

[Email](mailto:shmygov@rambler.ru)

[Сайт](https://github.com/shmygov/browserpedals)

Точное расположение этого и других файлов, используемых программой, можно найти на информационной странице - первой странице, которая откроется в браузере после запуска программы.

В настоящее время поддерживаются следующие роли педалей: "Педаль Пауза/Воспроизведение" и "Педаль Возврата назад". Любой педали можно назначить любую из этих ролей. Можно использовать обе педали, или только одну. Все это делается автоматически путем запуска программы и следования инструкциям на экране.

(Технически, файл `auto_detected_pedals.txt` можно также редактировать вручную.)


## Изменение опций программы:

Текстовый файл `browserpedals_options.txt` содержит ряд опций, которые пользователь может менять, чтобы корректировать поведение программы. Этот файл расположен в директории редактируемых данных программы:

В среде Linux:
```
/home/<user_name>/.local/share/browserpedals/browserpedals_options.txt
```

В среде Windows:
```
C:\Users\<user_name>\AppData\Local\dmitrish\browserpedals\browserpedals_options.txt
```

Точное расположение этого и других файлов, используемых программой, можно найти на информационной странице - первой странице, которая откроется в браузере после запуска программы.

Имеющиеся опции:

*browser*: По умолчанию программа открывает браузер Firefox. Чтобы использовать другой браузер, в файле опций соответствующим образом поменяйте значение *value* опции *browser*. На данный момент программа тестировалась с браузерами Firefox, Chrome, и Edge.

*user_interface*: По умолчанию программа использует веб-браузер в качестве графического пользовательского интерфейса при распознавании педалей. Чтобы использовать командную строку для распознавания педалей, в файле опций поменяйте значение *value* опции *user_interface* с "browser" на "command_line".

*jump_back_sec*: По умолчанию при нажатии педали "возврат назад" видео отматывается назад на 5 секунд. Чтобы использовать другой временной скачок, в файле опций соответствующим образом поменяйте значение *value* опции *jump_back_sec*. Это может быть любое число, возможно с дробной частью.


## Данные браузера:

Когда данная программа открывает веб-браузер, используется пользовательский профиль отличный от профиля, используемого по умолчанию при открытии браузера обычным образом. Все данные браузера (включая пользовательские настройки, кэш браузера, историю, закладки, установленные расширения, и т.п.), используемые веб-браузерами, когда они открываются данной программой, хранятся в следующей директории. Если профиль здесь удалить, вместо него будет создан чистый профиль:

В среде Linux:
```
home/<user_name>/.local/share/browserpedals/profiles/
```

В среде Windows:
```
C:\Users\<user_name>\AppData\Local\dmitrish\browserpedals\profiles\
```

Точное расположение этого и других файлов, используемых программой, можно найти на информационной странице - первой странице, которая откроется в браузере после запуска программы.


## Установка веб-драйвера (опционно):

Программа поставляется с предустановленным веб-драйвером для браузера Firefox, поэтому если вы хотите использовать Firefox, он будет работать без каких-либо дополнительных действий. Однако, если вы хотите использовать другой браузер, например Chrome или Edge, вы должны установить соответствующий веб-драйвер вручную, как описано ниже. К тому же, в случае использования Chrome или Edge вы должны будете периодически обновлять веб-драйвер, чтобы его версия совпадала с текущей версией автоматически обновляемого браузера Chrome или Edge.

Установите веб-драйвер для браузера, который вы хотите использовать. Ссылки для загрузки приведены на сайте:

[Скачать веб-драйвер](https://www.selenium.dev/documentation/webdriver/getting_started/install_drivers/#quick-reference)

**Важно**: Для всех браузеров, кроме Firefox, версия файла веб-драйвера должна совпадать с текущей версией вашего браузера.

Откройте скачанный архив и извлеките файл веб-драйвера. Веб-драйвер для браузера Firefox обычно имеет имя `geckodriver`. Веб-драйвер для браузера Chrome обычно имеет имя `chromedriver`. Веб-драйвер для браузера Edge обычно имеет имя `msedgedriver.exe`.

Поместите файл веб-драйвера в соответствующую поддиректорию в директории данных программы:

В среде Linux:
```
/home/<user_name>/.local/share/browserpedals/web_driver/linux64
```

В среде Windows:
```
C:\Users\<user_name>\AppData\Local\dmitrish\browserpedals\web_driver\win64
```

Точное расположение этого и других файлов, используемых программой, можно найти на информационной странице - первой странице, которая откроется в браузере после запуска программы.


## Поддерживаемые платформы:

Данное ПО тестировалось на платформе Linux (Ubuntu) с браузерами Firefox и Chrome, и на платформе Windows с браузерами Firefox, Chrome, и Edge.

Программа использует следующее программное обеспечение (Если программа устанавливается с использованием PIP, все устанавливается автоматически):

Проект Selenium для управления браузером:

[https://www.selenium.dev/selenium/docs/api/py/api.html](https://www.selenium.dev/selenium/docs/api/py/api.html)

Пакет "evdev" для управления педалями (если используется Linux):

[https://pypi.org/project/evdev/](https://pypi.org/project/evdev/)

[https://github.com/gvalkov/python-evdev](https://github.com/gvalkov/python-evdev)

[https://python-evdev.readthedocs.io/en/latest/](https://python-evdev.readthedocs.io/en/latest/)

Пакет "PyWinUSB" для управления педалями (если используется Windows):

[https://pypi.org/project/pywinusb/](https://pypi.org/project/pywinusb/)

[https://github.com/rene-aguirre/pywinusb](https://github.com/rene-aguirre/pywinusb)


