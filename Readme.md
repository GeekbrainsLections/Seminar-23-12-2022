# Инструкция по работе с Git

## Что такое гит?
***Git*** - самая популярная реализация распределённой системы контроля версий(версионность поддерживается и на сервере, и у каждого клиента). Самой распространнённой реализацией ***Git*** является (GitHub)[https://github.com]

## Подготовка репозитория
Для создания репозитория используется команда *git init*. Для этого необходимо открыть в терминале папку с будущем репозиторием и написать *git init*

## Создание коммитов

### Добавление файлов к коммиту
Для добавления файла к новому коммиту используется команда *git add*. Используется она следующим образом: в терминале с папкой-репозиторием пишем *git add <название файла>*.

### Создание коммита
Для создание новой фиксации(коммита) используется команда *git commit*. Для этого в терминале с папкой-репозиторием пишем *git commit -m "<сообщение к коммиту>*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО!!!***

## Журнал изменений
Для просмотра истории изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо написать *git log*

## Перемещение между коммитами
Для перемещения на другую фиксацию(коммит) используется команда *git checkout*. Для этого необходимо, как показано в прошлом пункте, в журнале изменений найти необходимый коммит и его хеш(номер), после чего в терминале с папкой-репозиторием надо написать *git checkout <хеш коммита>*. После выполнения этой команды мы попадаем в состояние **detached head**, в котором никакие следующие коммиты сохраняться не будут. Для выхода из этого состояния необходимо написать *git checkout master*.

## Ветки в гит
### Создание веток в гит
Для создание новой ветки используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>*.
### Просмотр списка веток
Для просмотра списка веток используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch*. Выделенная зелёным со звёздочкой ветка - это ветка, в данный момент на которой мы находимся.

### Перемещение между ветками
Для перехода на другую ветку используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <название ветки>*. Такая ветка должна **существовать**.

## Слияние веток и разрешение конфликтов
### Слияние веток
Основная цель создание дополнительных веток – проработать отдельный элемент проекта автономно, а затем присоединить его к проекту. Поэтому в большинстве случаев эти ветки в конечном итоге объединяются с веткой *master*. Процедура объединения веток называется слияние *(merge)*.

Для слияния текущей ветки с какой-либо другой используется команда *git merge <имя_ветки>*.

В результате выполнения этой команды в текущей ветке появится новый коммит. Этот коммит будет иметь два предка – последние коммиты обоих веток, участвующих в слиянии. Содержимое этого коммита будет включать содержимое коммитов обоих веток.

### Разрешение конфликтов
Общие сведения о конфликтах слияния.

Слияние и конфликты являются неотъемлемой частью работы с ***Git***. В большинстве случаев ***Git*** самостоятельно решает, как автоматически интегрировать новые изменения.

* Самый простой способ разрешить конфликт — отредактировать конфликтующий файл. Сделать это можно непосредственно в папке-репозитории. Для завершения слияния необходимо создать новый коммит.

* Второй способ - принять предложение ***Git***:
 1. Принять текущии изменения.
 2. Принять исходные изменения.
 3. Принять оба варианта.

### Удаление веток
Для того чтобы удалить ветку в ***Git*** используется команда *git branch -d <имя_ветки>*.

### Работа с удаленными репозитариями
Удаленный репозиторий – полноценный репозиторий, ничем не отличающийся от локального. У удаленного репозитория есть собственные ветки, собственный указатель ***HEAD***, своя история коммитов и так далее.
Если мы подключим удаленный репозиторий к своему локальному, то у нас появятся копии всех ссылочных объектов удаленного репозитория. То есть, например, у удаленного репозитория есть ветка *main*, а у нас будет копия этой ветки – *origin/main*. Все такие ссылочные объекты (указатели, ветки и теги) удаленного репозитория хранятся почти там же, где и у локального – в директории *.git/refs/remotes/<имя_удаленного_репозитория>*.
Для того, чтобы добавить удалённый репозиторий и присвоить ему имя *(shortname)*, необходимо выполнить команду *git remote add <shortname> <url>*.
  
