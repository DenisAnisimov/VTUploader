# VT Uploader

The VT Uploader utility is designed to upload executable files to the [virustotal.com](https://www.virustotal.com/) service and get reports on their analysis by various antivirus engines. To use the utility, you need to register on the virustotal.com website and obtain a personal key, which will grant you access to the service's API. Obtaining a key is a free procedure.

<p align="center"><img src="Img/VTUploader.png?raw=true"/></p>

## Working with the utility
### Options tab
* **Language** option allows you to select the utility's interface language.
* **API key** field is for entering the personal key obtained from the virustotal.com website.
* **Key information** button lets you view information about the key's owner and the current request limits for the virustotal.com service.
* **Warn when opening files with extensions NOT in the list** option warns the user against mistakenly opening files (e.g., photos) that may contain personal data. After uploading a file with personal data to the virustotal.com service, it can be accessed by an unlimited number of people, which could lead to a leak of this personal data. When a file is opened, its extension is checked, and if it's not on the list, a warning message will appear. However, the list of extensions will be ignored if an executable **PE**/**ELF**/**Macho** file with a non-standard extension is opened.
* **Load last report when opening file** option determines the utility's behavior when a file is opened. If this option is enabled, a request for the last report on the file will be made immediately upon opening it. If the option is disabled, the report request will only be made when you click the **Load last report** button.
* **Request reanalyze if file was analyzed more than N days ago** option allows for automatic reanalysis of a file. It's important to understand that file analysis is a slow procedure, and its speed depends on the load of the virustotal.com service. In general, it's not recommended to enable this option; if reanalysis is needed, it should be requested manually with the **Request reanalysis** button.
* **Create a subitem in the "Send to" menu** and **Delete the subitem in the "Send to" menu** buttons allow you to create and delete an additional VT Uploader submenu item in the **Windows Explorer** context menu's **Send to** option. Selecting this submenu item will launch the utility and automatically open the file selected in **Explorer**.

Settings can be stored in two places. If there's a file with the same name and an **ini** extension in the utility's folder, the utility will use this file to store settings, and the **API key** will be written in plain text without encryption. If the **ini** file is absent, the utility will use the registry to store settings, and the **API key** will be written in encrypted form.

### File tab

* **Select** button lets you choose the executable file you want to check on the virustotal.com website. Clicking the arrow on the right side of the button will bring up a menu where you can also choose the **Select process** option. Selecting this option will open a window where you can choose a currently running process, whose file should be opened. You can also open a file using the Drag&Drop mouse operation.
* After opening a file, the utility will calculate and display the **MD5** and **SHA-256** checksums. The utility's subsequent behavior depends on the **Load last report when opening file** option. If the option is not enabled, the utility will show the **Load last report** button, which you can click to load the last report. If it's enabled, the utility will immediately load the last report on the file. Important! No matter how the last report is obtained, if the file has not been previously uploaded to the virustotal.com service, it will be uploaded automatically.
* After loading the report, the utility will display its contents. The date of the last report, the number of antivirus engines that detected malicious content, and a list of all antivirus engines, their versions, and verdicts will be shown.
* **Copy** buttons allow you to copy data from the report to the clipboard.
* **View raw report** button lets you view the last report in its original JSON format.
* **Request reanalysis** button asks the virustotal.com service to perform a reanalysis of the file. It's important to understand that file analysis is a slow procedure, and its speed depends on the load of the virustotal.com service.
* **Open last report on virustotal.com** button launches your browser and opens the page on the virustotal.com website with the last report for the executable file.

---

Утилита VT Uploader предназначена для загрузки исполняемых файлов на сервис [virustotal.com](https://www.virustotal.com/)  и получения отчетов об их анализе различными антивирусными движками. Для работы утилиты необходимо зарегистрироваться на сайте virustotal.com и получить персональный ключ, который позволит получить доступ к API сервиса. Получение ключа является бесплатной процедурой.

## Работа с утилитой
### Вкладка Настройки
* Опция **Language** позволяет выбрать язык интерфейса утилиты.
* Поле **Ключ доступа к API** предназначено для ввода персонального ключа, полученного на сайте virustotal.com.
* Кнопка **Информация о ключе** позволяет просмотреть информацию о владельце ключа и текущих лимитах запросов к сервису virustotal.com.
* Опция **Предупреждать об открытии файлов с расширениями, НЕ входящими в список** позволяет предупредить пользователя от ошибочном открытии файлов (например, фотографий), которые могут содержать персональные данные. После загрузки файла с персональными данными на сервис virustotal.com доступ к нему может быть осуществлен неограниченным кругом лиц, и это может привести к утечке этих персональных данных. При открытии файла проверяется расширение файла, и если оно не входит в список, то появится предупреждающее сообщение. Но список расширений будет проигнорирован, если открывается исполняемый **PE**/**ELF**/**Macho** файл с нестандартным расширением.
* Опция **Загружать последний отчет при открытии файла** определяет поведение утилиты при открытии файла. Если данная опция включена, то при открытии файла сразу же будет произведен запрос последнего отчета о файле. Если опция отключена, то запрос отчета будет производится только при нажатии на кнопку **Загрузить последний отчет**.
* Опция **Запрашивать повторный анализ, если последний анализ был произведен более N дней назад** позволяет производить автоматический повторный анализ файла. Важно понимать, что анализ файла – это медленная процедура, скорость которой зависит от загруженности сервиса virustotal.com. В общем случае не рекомендуется включать эту опцию, а при необходимости повторного анализа файла запрашивать его вручную кнопкой **Запросить повторный отчет**.
* Кнопки **Создать подпункт в меню Отправить** и **Удалить подпункт в меню Отправить** позволяют создать и удалить в контекстном меню **Проводника** в пункте **Отправить** дополнительный подпункт **VT Uploader**. Выбор этого подпункта позволяет запустить утилиту и автоматически открыть в ней выбранный в **Проводнике** файл.

Настройки могут храниться в двух местах. При наличии в папке утилиты одноименного файла с расширением **ini** утилита будет использовать этот файл для хранения настроек, при этом **ключ доступа к API** будет записан в текстовом виде без шифрования. При отсутствии **ini** файла утилита будет использовать реестр для хранения настроек, при этом **ключ доступа к API** будет записан в зашифрованном виде.
### Вкладка Файл
* Кнопка **Выбрать** позволяет выбрать исполняемый файл, который необходимо проверить на сайте virustotal.com. При нажатии на стрелку в правой части кнопки появится меню, в котором дополнительно можно выбрать вариант **Выбрать процесс**. При выборе этого варианта появится окно, в котором можно выбрать уже запущенный процесс, файл которого должен быть открыт. Также файл можно открыть используя операцию мыши Drag&Drop.
* После открытия файла утилита произведет расчет контрольных сумм **MD5** и **SHA-256** и отобразит их. Дальнейшее поведение утилиты зависит от опции **Загружать последний отчет при открытии файла**. Если опция не включена, то утилита покажет кнопку **Загрузить последний отчет**, нажав на которую можно загрузить последний отчет. Если же включена, то утилита сразу же загрузит последний отчет о файле. Важно! Не зависимо от того, каким способом получается последний отчет, если файл не был ранее загружен на сервис virustotal.com, то он будет автоматически загружен.
* После загрузки отчета утилита покажет его содержимое. Будет отображена дата последнего отчета, количество антивирусных движков, определивших вредоносное содержание, и список всех антивирусных движков, их версий и вердиктов.
* Кнопки **Копировать** позволяют скопировать данные из отчета в буфер обмена.
* Кнопка **Посмотреть сырой отчет** позволяет просмотреть последний отчет в исходном **JSON** формате.
* Кнопка **Запросить повторный анализ** запрашивает у сервиса virustotal.com произвести повторный анализ файла. Важно понимать, что анализ файла – это медленная процедура, скорость которой зависит от загруженности сервиса virustotal.com.
* Кнопка **Открыть последний отчет на сайте virustotal.com** запускает браузер и открывает в нем страничку на сайте virustotal.com с последним отчетом об исполняемом файле.

