# Шпаргалка по работе с Git<br>
### Файл создаётся студентом группы ИСП-3.2 Максосом<br>
---
## Базовые команды в Git Bush:<br>
* **ls** _(от англ. list directory contents — «отобразить содержимое директории»)_ - Вывести содержимое папок в директории.<br>
* **ls -a** - Вывести скрытое содержимое папок в директории.<br>
* **ls~** - Вывести содержимое домашней директории из любого места.<br>
* **ls ..** - Вывести содрежимое предыдущей директории.<br>
* **cd** _(от англ. change directory — «сменить директорию»)_ - Сменить директорию.<br>
* **cd~** - Перейти в домашнюю директорию.<br>
* **cd ..** - Перейти на уровень выше.<br>
* **cd .** - Обратиться к текущей директории _(требуется для запуска файлов .exe или скриптов)_.<br>
* **pwd** _(от англ. print working directory — «показать рабочую папку»)_ - Вывести путь к текущей директории.<br>

## Работа с файлами:<br>
* **touch** - Создать файл в директории. _Пример: touch text.txt index.html style.css first-project. Данная команда создаёт файлы text.txt, index.html, style.css в папке first-project_<br>
* **mkdir** - Создать папку в директории.
* **mkrir -p** Создать структуру директорий. _Пример: mkdir -p dir1/dir-inside/dir-deeper-inside_<br>

**_Комманды touch и mkdir также могут работать сразу с домашней директорией и директорией ниже при помощи флагов "~" и ".."_**<br>

* **cp** - Скопировать файлы или целые папки.<br>
* **mv** - Переместить файлы или целые папки.<br>
* **cat** _(от англ. concatenate and print — «объединить и распечатать»)_ - Вывести содержимое текстового файла в консоль.<br>

### Удаление файлов и папок:<br>
* **rm** _(от англ. remove — «удалить»)_ - Удалить файл.<br>
* **rm -r** _ (-r — от англ. recursive, «рекурсивный»)_ - Рекурсивно удалить файлы и папки.<br>
* **rmdir** - Удалить директорию файлов.<br>

## Инициализация репозитория:<br>
* **git init** _(от англ. initialize, «инициализировать»)_ — Инициализировать репозиторий.<br>

## Синхронизация локального и удалённого репозиториев:<br>
* **git remote add origin https://github.com/** _(от англ. remote, «удалённый» + add, «добавить»)_ — Привязать локальный репозиторий к удалённому с URL https://github.com/<br>
* **git remote -v** _(от англ. verbose, «подробный»)_ — Проверить, что репозитории действительно связались;<br>
* **git push -u origin main** _(от англ. push, «толкать»)_ — В первый раз загрузить все коммиты из локального репозитория в удалённый с названием origin.<br>

**_Ваша ветка может называться master, а не main. Подправьте команду, если это необходимо._**<br>

* **git push** _(от англ. push, «толкать»)_ — Загрузить коммиты в удалённый репозиторий после того, как он был привязан с помощью флага -u.<br>

## Подготовка файла к коммиту:<br>
* **git add todo.txt** _(от англ. add, «добавить»)_ — Подготовить файл todo.txt к коммиту;<br>
* **git add --all** _(от англ. add, «добавить» + all, «всё»)_ — Подготовить к коммиту сразу все файлы, в которых были изменения, и все новые файлы;<br>
* **git add .** — Подготовить к коммиту текущую папку и все файлы в ней.<br>

## Создание и публикация коммита:<br>
* **git commit -m "Комментарий к коммиту."** _(от англ. commit, «совершать», фиксировать» + message, «сообщение»)_ — Сделать коммит и оставить комментарий, чтобы было проще понять, какие изменения сделаны;<br>
* **git push** _(от англ. push, «толкать»)_ — Добавить изменения в удалённый репозиторий.<br>

## Просмотр информации о коммитах:<br>
* **git log** _(от англ. log, «журнал [записей]»)_ — Вывести подробную историю коммитов;<br>
* **git log --oneline** _(от англ. log, «журнал [записей]» + oneline, «одной строкой»)_ — Показать краткую информацию о коммитах: сокращённый хеш и сообщение.<br>

## Просмотр состояния файлов:<br>
* **git status** _(от англ. status, «статус», «состояние»)_ — Показать текущее состояние репозитория.<br>

## Добавление изменений в последний коммит:<br>
* **git commit --amend --no-edit** _(от англ. amend, «исправить»)_ — Добавить изменения к последнему коммиту и оставь сообщение прежним;<br>
* **git commit --amend -m "Новое сообщение"** — Изменить сообщение к последнему коммиту на Новое сообщение.<br>

**_Выйти из редактора Vim: нажать Esc, ввести :qa!, нажать Enter._**

## «Откат» файлов и коммитов:<br>
* **git restore --staged hello.txt** _(от англ. restore, «восстановить»)_ — Перевести файл hello.txt из состояния staged обратно в untracked или modified;<br>
* **git restore hello.txt** — Вернуть файл hello.txt к последней версии, которая была сохранена через git commit или git add;<br>
* **git reset --hard b576d89** _(от англ. reset, «сброс», «обнуление» + hard, «суровый»)_ — Удалить все незакоммиченные изменения из staging и «рабочей зоны» вплоть до указанного коммита.<br>

## Просмотр изменений:<br>
* **git diff** _(от англ. difference, «отличие», «разница»)_ — Показать изменения в «рабочей зоне», то есть в modified-файлах;<br>
* **git diff a9928ab 11bada1** — Вывести разницу между двумя коммитами;<br>
* **git diff --staged** — Показать изменения, которые добавлены в staged-файлах.<br>

## Клонирование репозиториев Git:<br>
* **git clone git@github.com:GMaxoxo/** _(от англ. clone — «клон», «копия»)._ - Создать копию удалённого репозитория на вашем компьютере.<br>
* **git remote -v** - Проверить связаны ли репозитории.<br>

## Работа с ветками Git:<br>
* **git branch** - Просмотреть все ветки и узнать, где находитесь вы.<br>
* **git branch <название_ветки>** - Создать новую ветку.<br>

**_Название ветки в Git может состоять из букв, цифр, а также включать любой из четырёх символов: ., -, _, /. Эти символы не несут особого смысла. Например, ветка feature/add-branch-info могла бы называться feature_add-branch-info или feature-add-branch. Обратите внимание, что ветки не образуют иерархии, как директории, разделённые символом /. Главная ветка в проете будет называться либо master, либо main. Зависит от настроек системы._**<br> 

* **git checkout Название ветки** - Переключиться на другую ветку.<br>
* **git checkout -b <название_ветки>** - Создать ветку и сразу переключиться на неё.<br> 
* **git diff <название_ветки1> <название_ветки2>** - Сравнить ветки в проекте.<br>

**_Сравнивать хеши комитов может быть неудобно, ведь в одной ветке их может быть много. Представьте: сначала вы выводите историю через git log, затем ищете в длинном списке хеши тех коммитов, которые хотите сравнить, и только потом выполняете git diff. Для облегчения этой задачи в Git есть суффикс навигации "~N", где N — это число. Он отсчитывает от заданного коммита N коммитов назад во времени. Нумерация начинается с нуля: "commit~0" — это сам коммит, "commit~1" — предыдущий, "commit~2" — предшествующий предыдущему и так далее. Например, "HEAD~1" — это следующий за текущим коммит. А "main~5" — это пятый коммит в ветке main, если считать с последнего выполненного коммита. На практике чаще нужен либо текущий коммит (HEAD), либо следующий за ним ("HEAD~1"). Для "~1" есть специальное сокращение "~" (без числа). То есть вместо "HEAD~1" обычно пишут просто HEAD~._**<br> 

* **git merge <название_ветки>** - Провести слияние веток<br>

**_Перед тем как начать процесс слияния, нужно перейти в ветку, куда должны добавиться изменения. Обычно это главная ветка. Перейдите в неё и вызовите команду git merge с именем присоединяемой ветки feature/diff в качестве параметра._**

* **git branch -D <название_ветки>** - Удалить ветку после слияния.<br>

**_У команды git branch -D есть более безопасный вариант с флагом -d. Он удалит ветку только если она была полностью объединена с другой — то есть если две ветки стали (или изначально были) частью одной истории. Например, если вы нечаянно создали ветку с неправильным названием, её можно удалить через git branch -d %имя_ветки%. _**<br> 


---

## От себя<br>
Саунды из Ковбоя Бибопа являются чем-то невероятным. Советую к прослушиванию, да и к просмотру тоже. Крайне приятная штучка<3