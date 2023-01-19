# Инструкция по работе с Git

## Что такое Git

***Git*** - это одна из реализаций распределённой системы контроля версий, поддерживающие как локальные, так и удалённые репозитории. Самая популярная реализация Git - это [GitHub](https://github.com)

## Подготовка репозитория

Для создания репозитория используется команда *git init*. Для этого необходимо открыть в терминале папку с будущим репозиторием и там написать *git init*

## Создание "сохранений"

## Определение состояния

Для просмотра информации о текущем состоянии используется команда *git status*. С помощью нее можно узнать, актуальна ли информация на репозитории, нет ли чего-то нового, что поменялось, и так далее.

### Выполнение коммита

Для того, чтобы выполнить коммит используется команда *git commit*. Для этого в терминале с папкой-репозиторием необходимо написать *git commit -m '<сообщение к коммиту>'*. Сообщение к коммиту писать ***обязательно!!!*** 

## Добавление файла к коммиту

Для добавления файла к коммиту используется команда *git add*. Для этого в терминале с папкой-репозиторием необходимо написать *git add <название файла>*.

## Исправление коммита

Если вы опечатались в комментарии или забыли добавить файл и заметили это сразу после того, как закоммитили изменения, вы легко можете это поправить при помощи *git commit —amend*. Эта команда добавит все из последнего коммита в область подготовленных файлов и попытается сделать новый коммит. Это дает вам возможность поправить комментарий или добавить недостающие файлы в область подготовленных файлов.

Для более сложных исправлений, например, не в последнем коммите или если вы успели отправить изменения на сервер, нужно использовать *git revert <commit_hash>*. Эта команда создаст коммит, отменяющий изменения, совершенные в коммите *<commit_hash>*. Самый последний коммит может быть доступен по алиасу HEAD - *git revert HEAD*
Самый последний коммит может быть доступен по алиасу HEAD:

## Журнал изменений
Для просмотра истории коммитов используется команда *git log*. Для этого в терминале с папкой-репозиторием пишем *git log*. В показанном журнале обязательно будут:
* Хэш (номер) коммита
* Дата и время коммита
* Автор коммита
* Текст сообщения к коммиту

## Перемещение между коммитами

Для перемещения между коммитами используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <хэш коммита>*. Хеш коммита можно взять из истории коммитов, про которую было рассказано в предыдущем пункте.

## Ветки в Git

### Создание новой ветки

Основная ветка в каждом репозитории называется master. Чтобы создать еще одну ветку, используем команду *git branch <name>*. Эта команда создаст новую ветку, точную копию ветки master.

### Информация о существующих ветках

Информация о существующих ветках выводится в терминал с помощью команды *git branch*.

### Переключение между ветками

Команда *Git checkout <branch_name>* позволяет нам переключаться между локальными ветками. 

## Слияние веток и разрешение конфликтов

Слияние веток проводится с помощью команды *git merge <branch_name>*. Важно помнить, что мы должны находится на той ветке, куда мы хотим переместить данные, а *<branch_name>* указать ту ветку, откуда мы хотим данные получить.  

Конфликты регулярно возникают при слиянии ветвей или при отправке чужого кода. Иногда конфликты исправляются автоматически, но обычно с этим приходится разбираться вручную — решать, какой код остается, а какой нужно удалить.
Над разделителем ======= мы видим последний (*HEAD (current change)*) коммит, а под ним - конфликтующий (*conflicts (incoming change)*). VS Code предложит нам сохранить один из вариантов или сохранить оба варианта. Также доступна опция сравнения и решение в *Merge Editor*.

После разрешения конфликта обязательно нужно провести коммит.

## Удаление веток
