# Программа для заполнения спецификаций в Excel
## Установка:
Поддержка версий Excel 2007 и выше, что будет в 2003 не проверял.
Для установки программы:
1. В любое удобное место скачать *все* файлы из папки *"Спецификация"* (по ссылке "releases" версия может быть не актуальной): 
	* ***"Спецификация Надстройка.xlam"*** 
	* ***"База данных.xlsx"*** 
	* ***"Template-Spec.xlsx"*** 
***Файлы должны лежать в одной папке***
2. Открываем ***"Спецификация Надстройка.xlam"*** , разрешаем работу макросов и подтверждаем установку надстройки.
3. Далее работа ведется с файлом **"Template-Spec.xlsx"**, при открытии документа Excel есть  кнопка "Создать спецификацию" на вкладке "Спецификация".
4. Для обновления просто заменяем файл надстройки новым.
## Описание программы
Шаблон для спецификации состоит из 5 листов
* Версии
* Спецификация
* Перенос (может быть скрыт)
* СО
* ВР
### Версии
В этом листе можно сохранить информацию о предыдущих версиях файла (функция не до конца отработана, могут быть ошибки)
### Спецификация
Это главный лист для составления спецификации, в него заносим всю необходимую информацию, и добавляем элементы из базы данных.
### Перенос
Это рабочий лист, используется только для ручного переноса спецификации – описано далее. Может быть скрыт.
### СО и ВР
Листы подготавливают для печати то, что заполнили на листе спецификация. Они разлинованы под ГОСТ, за исключением таблиц слева, они привязаны к ячейкам таблицы Excel, к сожалению, не нашел простого способа сделать эти таблицы по ГОСТу.
## Описание меню (вкладка на ленте Excel "Спецификация")
### Перенос спецификации.
1.	**Сохранить сегодня:** Сохраняет файл с новой датой в имени.
2.	**Перенос спецификации:** Подготовка спецификации к печати, аналог кнопки «Печать» на листе.
3.	**Создать спецификацию:** Создает новую спецификацию по умолчанию сохраняет в папку с надстройкой.
3.	**Стиль R1C1:** меняет стили таблиц Excel на R1C1 или A1 соответсвенно.
4.	**Позиции:** Корректирует позиции (сквозная нумерация)
### Версии.
1.	**Очистить всё:** Удаляет все версии файла, оставляет одну текущую.
2.	**Сохранить:** Сохраняет версию спецификации.
3.	**Список версий:** Показывает все сохраненные версии спецификации.
4.	**Заменить дату:** Меняет дату текущей версии файла - лист «Версии», если этого листа нет, создает лист и записывает информацию о первой версии.
5.	**Пакетная обработка:** Выполняет пакетную обработку записанных действий в нескольких файлах (или не пользоваться, или пользоваться аккуратно, плохая отладка).
6.	**Снятие блокировки:** Снимает блокировку на листе «Версии», если в этом есть необходимость.
### Работа с базой.
1.	**Переподключить** Переподключает базу данных из файла "База данных.xlsx".
2.	**Закрыть форму:** Принудительно выгрузить из памяти форму «Добавить из базы».
3.	**Добавить из базы:** Добавляет элемент из базы данных. Аналог кнопки на листе.
4.	**Сортировать базу:** Сортировка базы данных (после добавления новых элементов в базу).
5.	**Открыть базу:** Открывает файл базы данных для редактирования.
1.	Лист Спецификация
	1.	Перенос: Подготовка спецификации к печати, аналог кнопки «Перенос спецификации» в меню.
	2.	Добавить из базы: Добавляет элемент из базы данных. Аналог кнопки в меню.
	3.	Очистка: Очистка листов «СО», «ВР», «Перенос» на выбор.
	4.	Создать PDF СО и ВР: Создает PDF версии с листов СО и ВР одновременно. Сохраняется на рабочем столе в папке «PDF Спецификации».
2.	Лист Перенос (может быть скрыт) описание работы в «Правилах подготовки спецификации на печать» «В ручную»
	1.	Перенос по строкам.
	2.	Перенос по листам.
3.	Листы СО и ВР
	1.	Добавить лист: Добавляет лист в спецификацию.
	2.	Отправить на печать:
		1. «Печать листа» распечатает ТЕКУЩИЙ лист.
			1.	Если выбрана «Печать в PDF» Сохраняет лист как PDF на рабочем столе в папке «PDF Спецификации»
			2.	Если выбрана «Печать на А4, А3» отправляет на печать текущий лист на принтер по умолчанию.
		2.	Кнопка «Пакетная печать» Печатает на принтере по умолчанию или создает PDF файлы сразу у нескольких выбранных файлов (все параметры нужно задать)
## Правила заполнения спецификации:
1.	Спецификация заполняется на листе ***"Спецификация"*** строки в колонке "Наименования" пропускать **НЕЛЬЗЯ**.
2.	Если стоит позиция, то при переносе между "позициями" пропускается строка. Если Позиция отсутствует строка не пропускается. Возможен вариант, когда строки не пропускаются, это настраивается.
3.	Знак неразрывного пробела "_" пропадает на листах для печати.
4.	"вр" в строке позиции прописывается для создания "заметок" для ведомости объемов работ (лист ВР), игнорируется при создании "Спецификации" (лист СО).
5.	Если в колонках СО и ВР установлен (произвольный) символ, то при подготовке для печати с этого места будет перенос на новый лист.
6.	Если необходимо подчеркнуть строку вместо позиции ставим букву "ч". (ГОСТ 21.501-2011 5.7).
## Правила подготовки спецификации на печать:
### Автоматически (используется для новых спецификаций, если нет никаких изменений)
1.	Нажать «Печать» на листе, или «Перенос спецификации» в меню - Выбираем «На лист для печати».
2.	Где необходимо начать с нового листа добавляем разделитель в колонке "СО" и "ВР" (п. 6 правил заполнения)
3.	Если будет меньшее количество листов чем есть на листах СО и ВР то появляется запрос о необходимости удалить лишние. При нажатии "Нет" функция продолжает работать, но последние листы не удаляются.
### В ручную (используется в случае если в спецификация делаются изменения, устанавливаются маркеры и т.п., чтобы «не поехало» форматирование)
1.	Нажать «Перенос» на листе, или «Перенос спецификации» в меню - Выбираем «На лист перенос». 
1.	С листа «Перенос» 
	1.	Выбираем "Перенос по листам" (для первого листа НЕ использовать)
		1.	Выбираем Ячейку "Позиции" на листе Перенос с которой будем переносить.
		2.	На листе СО или ВР Выбираем **ЛЕВУЮ ВЕРХНУЮЮ** ячейку (сразу под ячейкой "Позиция") жмем ОК
		3.	Выбираем необходимое количество листов для переноса
		4.	**НЕ ИСПОЛЬЗОВАТЬ ДЛЯ ПЕРВОГО ЛИСТА!!!!**
2.	Для того чтобы перенести несколько строк выбираем "Перенос по строкам", выбирается все аналогично "Переносу по листам" только задается необходимое количество строк, а не листов, для переноса на первом листе использовать этот способ с указанием необоходимого переноса строк.
3.	Кнопка "Добавить лист" добавляет лист в СО или ВР 
***
## Работа с базой данных
### Добавление новых элементов
1.	Для редактирования базы открыть файл База данных.xlsx, Лист База_СО (имя не менять). В первых четырех колонках нельзя добавлять цифры. 
	* Поле «Примечание» - можно добавить необходимую информацию об элементе, отображается на форме, при наведении на «Тип оборудование материала» (после выбора элемента)
	* Поле «1» - просто порядковый номер элементов
	* Поле «Нов.» метка для новых элементов, чтобы их удобнее было найти (смысловой нагрузки не несет).
	* Поле «Сортировка» - Для сохранения порядка сортировки элементов внутри подкатегории (иногда Excel сортирует неправильно).
2.	После добавление элементов необходимо переподключить базу данных, кнопка "Переподключить" на вкладке спецификация.
### Добавление элементов в спецификацию
1.	На листе «Спецификация» жмем кнопку «Добавить из базы» или в меню с аналогичным названием.
2.	Выбираем необходимый элемент.
3.	Выбираем строку в которую необходимо вставить нашу позицию.
4.	И жмем кнопку вставить.
После работы макроса комбинация клавиш **Ctrl + Z (Отмена)** не работает, будьте внимательны к содержимому.
***
По умолчанию форма не выгружается из памяти, поэтому если появляются проблемы с отображением формы (обычно такое встречается, когда параллельно работаешь с несколькими листами), то форму надо «принудительно закрыть» кнопка «Закрыть форму» на вкладке Спецификация – Работа с базой 
***