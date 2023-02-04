 # Инструкция по работе с Git

 ## Что такое Git?
 Самая популярная реализация  распределенной системы контроля версий (версионность поддерживается и на сервере, и у каждого клиента). Самой распространенной реализацией гит является (*GitHub*)

 ## Подготовка репозитория
 Для создания репозитория используется команда *git init*. Для этого необходимо открыть в терминале папку с будущим репозиторием и написать *git init*.

 ### Добавление файлов к коммиту
 Для добавления файла к новому коммиту используется команда "git add". Используется она следующим образом: в терминале с папкой-репозиторием используем "git add <название файла>"

 ## Журнал изменений
 Для просмотра истории изменений используется команда git log. Для этого в терминале с папкой-репозиторием необходимо написать git log.

 ## Ветвление в Git - Управление ветками

 Kоманда git branch делает несколько больше, чем просто создаёт и удаляет ветки. При запуске без параметров, вы получите простой список имеющихся у вас веток.
 Cимвол *, стоящий перед веткой master: он указывает на ветку, на которой вы находитесь в настоящий момент (т. е. ветку, на которую указывает HEAD). Это означает, что если вы сейчас сделаете коммит, ветка master переместится вперёд в соответствии с вашими последними изменениями. Чтобы посмотреть последний коммит на каждой из веток, выполните команду git branch -v.

 Опции --merged и --no-merged могут отфильтровать этот список для вывода только тех веток, которые слиты или ещё не слиты в текущую ветку. Чтобы посмотреть те ветки, которые вы уже слили с текущей, можете выполнить команду git branch --merged.

 Переименуйте локальную ветку master в main с помощью следующей команды:

git branch --move master main
После этого, локальной ветки master больше не существует, потому что она была переименована в ветку main.

Чтобы все остальные могли видеть новую ветку main, вам нужно отправить её в общий репозиторий. Это делает переименованную ветку доступной в удалённом репозитории.


 ## Удаление веток
Удаление локальной ветви с помощью git branch -d команды при извлечении в другую ветвь. Для удаления удаленной ветви требуется использовать git push команду с параметром --delete

## Добавление нового удаленного репозитория
Чтобы добавить новый удаленный репозиторий, выполните команду git remote add в терминале в каталоге, в котором хранится репозиторий.

Команда git remote add принимает два аргумента:
имя удаленного репозитория, например, origin;
URL-адрес удаленного репозитория, например, https://github.com/user/repo.git.

## Удаление удаленного репозитория
Чтобы удалить удаленный URL-адрес из репозитория, используйте команду git remote rm.

Команда git remote rm принимает один аргумент:

имя удаленного репозитория, например, destination.
При удалении удаленного URL-адреса из репозитория выполняется только отмена привязки для локальных и удаленных репозиториев. Сам удаленный репозиторий не удаляется.

## Выбор URL-адреса для удаленного репозитория
Существует несколько способов клонирования репозиториев, доступных в GitHub.com.

При просмотре репозитория во время входа в учетную запись под сведениями о репозитории отображаются URL-адреса, которые можно использовать для клонирования проекта на компьютер.

Сведения о настройке или изменении удаленного URL-адреса см. в разделе Управление удаленными репозиториями.