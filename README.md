# Report Box

Report Box – это консольный, хардкорный, но очень эффективный Python-скрипт, позволяющий делать в основном три вещи: 1) очень быстро вводить отчеты возвещателей с помощью автоматизации нажатий на клавиатуру; 2) смотреть, кто еще не сдал отчет; 3) генерировать общий отчет для ввода на сайте. Программа подходит тем, кто дружит с клавиатурой и может потратить 10 минут на чтение документации. В принципе, эти качества должны быть у каждого секретаря. 😅

![enter image description here](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgdDMANp-O41IGGhyphenhyphenzAA8J44qGLwslIZARN6HlVlFqZPK5LqqEtO1TObH6CGH08MelkJDfJ3SlqvffYi4NLLDN0U_awT8B3ZWNVrY2ACXSbOiibCXCsj12Qiwpot-eMh_tp_TsAsYtwz66evBBL-GtcDT9oCX_kOk8NREhbKjg97re5TlE3CqyFKHHLtzJI/s636/rocket_box.png)

## Установка и начало работы

1. Если в системе нет Python, установите его. Прямая ссылка для Windows: [python-3.8.6-amd64-webinstall.exe](https://www.python.org/ftp/python/3.8.6/python-3.8.6-amd64-webinstall.exe).
2. Скачайте и запустите файл программы: [reportbox.py](https://github.com/antorix/Report-Box/releases/download/release/reportbox.py).
3. Программа создаст папки `Возвещатели`, `Подсобные пионеры` и `Общие пионеры`. Скопируйте в них PDF-файлы соответствующих возвещателей.

Можно начинать работать! Вверху экрана программы есть подсказки по всем командам. В принципе, этого достаточно для работы, но еще несколько пояснений, если вам интересно углубиться в детали или не все понятно.

## Принципы работы

Report Box создает и поддерживает собственную базу данных путем сканирования PDF-файлов, и все операции выполняются с этой базой. Она находится в файле `publishers.ini`. Это фактически простой текстовый файл. Содержимое ваших PDF-файлов программа не видит и не изменяет (кроме единственного случая ввода отчета, описанного ниже). Важно понимать, что программа использует уже существующие, официальные PDF-бланки, и не пытается генерировать их сама. Когда вы копируете в папки новые бланки, они сразу появляются в программе (программа постоянно мониторит папки). Но настоятельно не рекомендуется переименовывать и удалять бланки вручную (особенно переименовывать), это может привести к неожиданным для вас последствиям. Обе эти операции нужно выполнять в программе. Для создания новых возвещателей нужно указать в программе местоположение бланка S-21_U.pdf. Если удалить файл `publishers.ini`, программа создаст свою базу с нуля – так можно начать с чистого листа.

### Как открыть возвещателя

Чтобы открыть любого возвещателя, введите название его файла (без части `.PDF`) и нажмите Enter. Можно ввести даже частично. Скажем, если файл называется `1КА`, то можно ввести и `КА`, и даже `А` (регистр не важен). Но если будет несколько совпадений, вам будет предложено выбрать из списка. Затем появится меню действий, которые можно выполнить с возвещателем. Выбор осуществляется путем ввода номера и нажатия Enter.

### Как ввести отчет

Это самая важная часть. Отчет вводится в одной-единственной строке. Сначала вводите название файла, как упоминалось выше, а затем через пробел – количество часов. Например: `Иван 5`. Если нужно ввести изучение, вводите его дальше через еще один пробел: `Иван 5 1`. Если это пионер и у него есть кредит часов, вводите его следующим: `Иван 50 1 10`. Если любое значение отсутствует, вводите ноль. (Вместо пробелов можно использовать табуляцию.)

Когда вы нажимаете `Enter`, программа сама открывает PDF-файл этого возвещателя. А затем происходит главное волшебство: **поставьте курсор мыши в поле «Часы» соответствующего месяца и нажмите на кнопку «Insert» на клавиатуре**. Вы увидите, как отчет целиком ввелся в PDF-файл. Вам останется его только сохранить.

Если у вас остались вопросы или что-то не работает, пишите на [inoblogger@gmail.com](mailto:inoblogger@gmail.com).
