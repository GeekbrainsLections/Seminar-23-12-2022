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
Для слияния двух веток используется команда *git merge*. Для этого в терминале с папкой-репозиторием пишем *git merge <название ветки>*. __*Слияние происходит с той веткой, на которой вы находитесь на данный момент*__.

### Разрешение конфликта
При выполнении слияния между двумя ветками возможно возниновения конфликта. Это связано с различиях, имеющихся в этих ветках. Такое состояние называется *conflicting state - __состояние конфликта__*. Для разрешения конфликта существуют два способа.

#### Встроенная утилита
В Visual Studio Code есть встроенная утилита __*Merge Editor*__, которая предлагает четыре опции разрешения конфликта.

1. _**Принять текущие изменения**_ - то есть оставить данные введенные на текущей ветке, игнорировать данные той ветки, с которой происходит слияние, *в таком случае данные сливаемой ветки стираются*.
2. _**Принять входящие изменения**_ - заменить данные, введенные на текущей ветке данными, введенными на ветке с которой происходит слияние, *в таком случае данные текущей ветки стираются*.
3. _**Принять оба изменения**_ - позволяет сохранить все данные из сливаемых веток, *в этом случае данные текущей ветки идут первыми, после - данные из сливаемой ветки*
4. _**Сравнить изменения**_ - просмотр данных двух веток одновременно, *с возможностью вручную убрать или оставить необходимые данные*.

#### Редактирование вручную
Для редактирования вручную нужно в поле текстового редактора удалить ненужные данные, затем сохранить полученный файл и создать коммит через последовательность git add<название файла>; git commit -m <сообщение к коммиту>. __*Удаляя ненужные данные также не забывайте удалить системные строчки HEAD (current change), <название сливаемой ветки> (incoming change), а также разделительную строчку между двумя в виде знаков равенства (=)*__.

## Удаление веток

## Удаление веток
Для удаления ветки используется команда *git branch -d*, ***-d в данной команде - сокращение delete (удаление)***. Для этого в терминале с папкой-репозиторием пишем *git branch <название ветки>. В случае успешного удаления ветки терминал выдаст сообщение __Deleted branch <название ветки> (was <хеш коммита>)__, *в круглых скобках отображен актуальный хеш (номер) коммита, который был закреплен за удаленной веткой*.
