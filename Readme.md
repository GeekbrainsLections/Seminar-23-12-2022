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

### Переключение между ветками
(Просмотр списка веток)

Сейчас, если мы напишем команду *git branch*, мы увидим две доступные ветки:

amazing_new_feature
* master

master — это активная ветка, она помечена звездочкой. Но мы хотим работать с нашей “новой потрясающей фичей”, так что нам понадобится переключиться на другую ветку. Для этого воспользуемся командой *git checkout <имя новой ветки>*, она принимает один параметр — имя ветки, на которую необходимо переключиться. Пример: *git checkout amazing_new_feature*

В Git ветка — это отдельная линия разработки. Git checkout позволяет нам переключаться между ветками. Это один из способов получить доступ к работе коллеги или соавтора. Однако тут надо помнить, что пока вы не закомитили изменения, вы не сможете переключиться на другую ветку. 

 ## Слияние веток

Слияние веток поисходит с помощью команды *git merge <имя ветки>*, указывается имя той ветки, которую сливаем с текущей веткой

## Слияние веток и разрешение конфликтов

Конфликты регулярно возникают при слиянии ветвей. Иногда конфликты исправляются автоматически, но обычно с этим приходится разбираться вручную — решать, какой код остается, а какой нужно удалить. Для этого программа предлагает вариант замены, который можно выбрать, либо внести изменения самому, вручную отредактировав или объединив предложенные варианты.

Пример:
Приложение отметило строки, содержащие конфликт:

<<<<<<< HEAD 
// Use a for loop to console.log contents. for(var i=0; i<arr.length; i++) { console.log(arr[i]);

======= 

 // Use forEach to console.log contents. arr.forEach(function(item) { console.log(item); }); 
 />>>>>>Tim's commit.

Над разделителем ======= мы видим последний (HEAD) коммит, а под ним - конфликтующий. Таким образом, мы можем увидеть, чем они отличаются и решать, какая версия лучше. Или вовсе написать новую. В этой ситуации мы так и поступим, перепишем все, удалив разделители, и дадим git понять, что закончили.

Когда все готово, нужно закоммитить изменения, чтобы закончить процесс

## Удаление веток

