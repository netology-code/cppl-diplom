# Курсовой проект "Парсер INI-файлов"

Курсовой проект представляет собой простой парсер файлов формата INI.

## Содержание

### 1. Введение
INI-файлы — это обычные текстовые файлы, которые можно редактировать и просматривать при помощи любого текстового редактора.
INI файлы приобрели популярность в Windows, они могут использоваться в любой ОС. Несложная структура этого формата позволяет легко обрабатывать их программно и имеет достаточно понятный вид для чтения и изменения человеком.

### 2. Формат INI-файлов
INI-файлы могут содержать следующие типы строк:
* Строка имени секции - обозначает имя новой секции переменных. Имеет следующий формат: 
` [имя_секции] ` <br/>
Пробелы и символы табуляции, стоящие до открывающей и после закрывающей скобки игнорируются.

* Строка задания переменной - задаёт значение переменной. Имеет следующий формат:
` название_переменной = значение_переменной ` <br /> 
Количество пробелов между символами равенства может быть произвольным.
Для простоты будем считать, что значения могут быть либо строкой, либо числом. Несколько значений не допускается.

* Строка комментариев. Имеет следующий формат: <br /> 
` ; строка комментариев ` <br/>
Парсер должен игнорировать такие строки, с ними ничего делать не нужно

### 3. Общая структура INI-файла
Пример структуры INI-файла:
```INI
[Section1]
; комментарий о разделе
var1=5.0 ; иногда допускается комментарий к отдельному параметру
var2=какая-то строка
  
[Section2]
var1=1
var2=значение_2

; Иногда значения отсутствуют 
[Section3]
[Section4]
Mode=
Vid=

; Секции могут повторяться
[Section1]
var3=значение
var1=1.0 ; переприсваиваем значение
```

### 4. Пример работы парсера
Вам нужно реализовать класс парсера INI-файлов, который предоставляет для пользователя одну шаблонную функцию, позволяющую получить значение переменной в определённой секции. 
 ```C++
ini_parser parser("filename");
auto value = parser.get_value<int>("section.value")
 ```
 ______
 
 #### Напоминаем, что работу можно сдавать частями
 ______

### Как правильно задавать вопросы преподавателю?

Что поможет решить большинство частых проблем:

1. Работа над проектом объемная. Вы можете сдавать работу на проверку: частями или полностью. Вы можете сдать часть кода и получить обратную связь, после чего работа будет отправлена на доработку и вы сможете продолжить. 
2. При возникновении вопросов попробовать найти ответ сначала самому в интернете. Умение искать ответы пригодится вам в профессиональной деятельности. После самостоятельного поиска можно спрашивать преподавателя.
3. Если вопросов больше одного, то присылайте их в виде нумерованного списка. Так дипломному руководителю будет проще отвечать на каждый из них.
4. При необходимости прикрепите к вопросу скриншоты и стрелочкой покажите, где не получается. Программу для этого можно скачать [здесь](https://app.prntscr.com/ru).
5. Распределяйте нагрузку, планируйте время на обучение и начинайте работу над курсовой как можно раньше, чтобы у вас было больше времени на правки и доработку проекта.

Что может стать источником проблем:

1. Вопросы вида «Ничего не работает. Не запускается. Всё сломалось». Преподаватель не сможет ответить на такой вопрос без дополнительных уточнений. Цените своё время и время других.
2. Откладывание выполнения курсового проекта на последний момент.
3. Ожидание моментального ответа на свой вопрос. Преподаватели — работающие разработчики, которые кроме преподавания занимаются рабочими проектами. Их время ограничено, поэтому постарайтесь задавать правильные вопросы, чтобы получать быстрые ответы :)

______

### Инструкция по сдаче курсовой работы

1. Выполняйте работу в [GitHub](https://github.com/)
2. Скопированную ссылку (вашу курсовую работу) нужно отправить на проверку. Для этого перейдите в личный кабинет на сайте [netology.ru](http://netology.ru/), в поле комментария к домашней работе вставьте скопированную ссылку и отправьте работу на проверку.
3. Работу можно сдавать частями

### Критерии оценки:

1. К личном кабинете для сдачи прикреплена ссылка с кодом курсовой работы
2. В ссылке должен содержаться код, который при запуске выполняет описанный в задании алгоритм
