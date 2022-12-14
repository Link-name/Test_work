# **Инструкция по работе с Git**
![](i.webp)

*Ввидение:* 

<span style="color:green">**Перед началом работы нужно выполнить некоторые настройки:**

***git config --global user.name "Your Name"*** - указать имя, которым будут подписаны коммиты
git config --global user.email"e@w.com"  # указать электропочту, которая будет в описании коммитера
Если вы в Windows:

***git config --global core.autocrlf true*** - включить преобразование окончаний строк из CRLF в LF

 ## <span style="color:green"> 1.  Иницилизация репозитория.

*Репозиторий* - это хранилище, папка проекта, отслеживаемого Git, содержащая дерево изменений проекта в хронологическом порядке. Все файлы истории хранятся в специальной папке .git/ внутри папки проекта. 


*Коммит* – фиксация изменений, внесенных в индекс. Другими словами, коммит – это единица изменений в вашем проекте. Коммит хранит измененные файлы, имя автора коммита и время, в которое был сделан коммит. Кроме того, каждый коммит имеет уникальный идентификатор, который позволяет в любое время к нему откатиться.

*Git init* - создает новый репозиторий. (подготовка к работе).   


## <span style="color:green">2. Проверка состояния репозитория. 
*<span style="color:yellow">git status* - команда отображает состояние рабочего коталога и раздела проидексировнных фаулов. С ее посощью можно проверить индексацию изменений и увидеть файлы которые не отслеживает git. 
Для инициализации (создания) репозитория используется команда: 
  

## <span style="color:green">3. Добавление в индекс.

***Индекс*** – файл, в котором содержатся изменения, подготовленные для добавления в коммит. Вы можете добавлять и убирать файлы из индекса.
Перед началом работы нужно выполнить некоторые настройки:

 *<span style="color:yellow">git add* -добавить в индекс все новые, изменённые, удалённые файлы из текущей директории и её поддиректорий.

*<span style="color:yellow">git add text.txt*  добавить в индекс указанный файл (был изменён, был удалён или это новый файл).

*<span style="color:yellow">git add -i* - запустить интерактивную оболочку для добавления в индекс только выбранных файлов.

*<span style="color:yellow">git add -p* - показать новые/изменённые файлы по очереди с указанием их изменений и вопросом об отслеживании/индексировании

- <span style="color:red">Удаление изменений из индекса. 

       git reset - убрать из индекса все добавленные в него изменения (в рабочей директории все изменения сохранятся), антипод git add
       git reset readme.txt  - убрать из индекса изменения указанного файла (в рабочей директории изменения сохранятся)


  - <span style="color:red">Отмена изменений. 
        
        git checkout text.txt - ОПАСНО: отменить изменения в файле, вернуть состояние файла, имеющееся в индексе
     
        git reset --hard - ОПАСНО: отменить изменения; вернуть то, что 
        в коммите, на который указывает HEAD (незакомиченные изменения удалены из индекса и из рабочей директории, неотслеживаемые файлы останутся на месте)
      
        git clean -df - удалить неотслеживаемые файлы и директории


## <span style="color:green">4.  Фиксация изменений. 
*<span style="color:yellow">git commit -m "Name of commit"*   -  зафиксировать в коммите проиндексированные изменения (закоммитить), добавить сообщение.

*<span style="color:yellow">git commit -a -m "Name of commit"* - проиндексировать отслеживаемые файлы (ТОЛЬКО отслеживаемые, но НЕ новые файлы) и закоммитить, добавить сообщение.

## <span style="color:green">5. Переключение на другой коммит и просмотр истории коммитов.

- Команды вывода и просмотра коммит.


*<span style="color:yellow">git log --shortstat* - Отображает только строку с количеством изменений/вставок/удалений для команды --stat.

Отображает только строку с количеством изменений/вставок/удалений для команды <span style="color:yellow">git log --stat.

*<span style="color:yellow">git log --name-only* - Показывает список измененных файлов после информации о коммите.

*<span style="color:yellow">git log --name-status* -Показывает список файлов, которые добавлены/изменены/удалены.

*<span style="color:yellow">git log --abbrev-commit* - Показывает только несколько символов SHA-1 чек-суммы вместо всех 40.

*<span style="color:yellow">git log --relative-date* - Отображает дату в относительном формате (например, «2 weeks ago») вместо стандартного формата даты.

*<span style="color:yellow">git log --graph* - Отображает ASCII граф с ветвлениями и историей слияний.

*<span style="color:yellow">git log --pretty* - Показывает коммиты в альтернативном формате. Возможные варианты опций: *<span style="color:yellow">"oneline, short, full, fuller и format* (с помощью последней можно указать свой формат).

*<span style="color:yellow">git log --oneline* - Сокращение для одновременного использования опций span <span style="color:yellow">--pretty=oneline --abbrev-commit.

*<span style="color:yellow">git log --oneline --all* - Выводим полный граф коммитов, отводя по одной строке на коммит.
- <span style="color:green">Переключиться на другой коммит и продолжить работу с него.

    Потребуется создание новой ветки, начинающейся с указанного коммита.
*<span style="color:yellow">git checkout b9533bb*  - переключиться на коммит с указанным хешем (переместить HEAD на указанный коммит, рабочую директорию вернуть к состоянию, на момент этого коммита)

*<span style="color:yellow">git checkout master*  - переключиться на коммит, на который указывает master (переместить HEAD на коммит, на который указывает master, рабочую директорию вернуть к состоянию на момент этого коммита)
 

 *<span style="color:yellow">git checkout -b new-branch 5589877*   - создать ветку new-branch, начинающуюся с коммита c хешем 5589877 (переместить HEAD на указанный коммит, рабочую директорию вернуть к состоянию, на момент этого коммита, создать указатель на этот коммит (ветку) с указанным именем).
 
## <span style="color:green">6. Проверка состояния изменений.

*<span style="color:yellow">git diff*               - сравнить рабочую директорию и индекс (неотслеживаемые файлы ИГНОРИРУЮТСЯ).

*<span style="color:yellow">git diff --color-words*  - сравнить рабочую директорию и индекс, показать отличия в словах (неотслеживаемые файлы ИГНОРИРУЮТСЯ).

*<span style="color:yellow">git diff index.html*     - сравни
ть файл из рабочей директории и индекс.

*<span style="color:yellow">git diff HEAD*           - сравнить рабочую директорию и коммит, на который указывает HEAD (неотслеживаемые файлы ИГНОРИРУЮТСЯ).

*<span style="color:yellow">git diff --staged*       - сравнить индекс и коммит с HEAD.

*<span style="color:yellow">git diff master feature* - посмотреть что сделано в ветке feature по сравнению с веткой master.

*<span style="color:yellow">git diff --name-only master feature* - посмотреть что сделано в ветке feature по сравнению с веткой master, показать только имена файлов.

*<span style="color:yellow">git diff master...feature* - посмотреть что сделано в ветке feature с момента (коммита) расхождения с master.


## <span style="color:green"> 7.  Добавление изображения. Создание и обьединение новых веток.

7.1. Инструкция по добовлению изобрадения. 
 Чтобы вставить изображение, достаточно написать следующее:

<span style="color:yellow">![ ] и (name imenges)

Так же что бы добавить файлы игнор нужно:
- создать файл с именем - <span style="color:yellow">.gitignore
- добавить имя файла который нужно игнорировать например - <span style="color:yellow"> name.webp
![Пример развитвлений и слияния веток в работе](i2.webp)

Пример: (рис. 1) 

7.2. Работа с новыми ветками.   
- Создание новой ветки.

<span style="color:yellow">**git branch (имя ветки)** - создание новой ветки с указанием имяни ветки.
- Удаление ветки.

<span style="color:yellow">**git branch -d (имя ветки)** - удаление выбранной ветки.
пше
- Слияние 2-х веток.

<span style="color:yellow">**git  merge (коммит)** - слияние 2х веток  (обязательно делать из коммита в который хотим сделать merge).
- Удобный вывод информации.

<span style="color:yellow">**git log --oneline --graph --all** - набор команд что бы увидить ветки мастер и созданную ветку и как проходило слияние веток. (удобный вариант).

<span style="color:orange">Смотри пример (рис.1 Работа с ветками).


# <span style="color:green"> 8. Дополнительная информация. Работа с Markdown.

     - Для оформления заголовков используют решётку. Одна решётка — заголовок  первого уровня, две — заголовок второго уровня, и так до пятого. #-1, ## - 2, ### - 3,      #### - 4.### 

    - Чтобы выделить слово или абзац, используют одну звёздочку в начале и в конце:

    * * → *вот так*

    - Если нужно выделить сильнее, берут две звёздочки:

    **   ** → **выделяем текст сильнее**

    - Зачёркивают двумя тильдами:

    ~~ ~~ → ~~зачеркнули и всё~~

    - Для оформления кода используют обратный апостроф: `.

     `` → `Пример кода`

    - Чтобы сделать ненумерованный список, каждый элемент начинают с символов *, - или +.

    - Изменение цвета выбранного обзаца  - <span style="color:yellow">
    
## Уделенные репозитории

Удаленные рапазитории нужны для совместной работы.
 А также для работы с удаленного места.
 Так же добавляю информацию, для понимания процесса!!!!
 Так же добавляю информацию, для понимания процесса!!!!
Так же добавляю информацию, для понимания процесса!!!!
 
 
 Так же добавляю информацию, для понимания процесса!!!!
