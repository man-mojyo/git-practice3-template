# Практика 3

## Подготовка к работе

Перед выполнением задания проверьте:

* имя пользователя аутентифицированного в GitHub с помощью **Диспетчера учетных данных** в панели управления Windows;
* имя и почту пользователя: `git config --global --list`.

При необходимости внесите необходимые изменения.

Создайте локальную копию репозитория с помощью команды `git clone <URL репозитория>`.

## Ход работы

1. Просмотр истории коммитов

   * Выполните команду `git log`, изучите её вывод.
   * Сделайте скриншот вывода команды `git log` и сохраните его в папку `1_log/`.

     Если вывод команды длинный и не помещается в одно окно, то его можно промотать. Чтобы выйти из режима просмотра длинного содержания нажмите клавишу `q`.

2. Исправление последнего коммита

   * Выполните поиск в Интернете и выберите лучший клиент Git.

   * Откройте в текстовом редакторе файл `git_clients.md` и впишите его название в первый пункт.

   * Сделайте коммит:

     ```
     git add git_clients.md
     git commit -m "Add best git client"
     ```
   * Сохраните историю коммитов:

     ```
     git log > 2_commit_amend/begin.txt
     ```

   Чтобы добавить изменения к уже созданному коммиту используется команда `git commit --amend`:

   * Добавьте ещё один клиент Git в файл `git_clients.md` (создайте для него второй пункт в новой строке).

   * Добавьте его к предыдущему коммиту с измением комментария:

     ```
     git add git_clients.md
     git commit --amend
     ```

   * Сохраните историю коммитов:

     ```
     git log > 2_commit_amend/end.txt
     ```

3. Отмена индексации файла

   * Добавьте третий клиент Git в файл `git_clients.md` (создайте для него пункт в новой строке).
   * Подготовьте файл к коммиту (не делайте сам коммит), проверьте и сохраните статус репозитория:

     ```
     git add git_clients.md
     git status
     git status > 3_restore/begin.txt
     ```

   * Отмените изменение, проверьте и сохраните статус репозитория.

     Чтобы отменить добавление (индексацию) файла перед коммитом используется команда `git restore --staged`:

     ```
     git restore --staged git_clients.md
     git status
     git status > 3_restore/end.txt
     ```

   * Сделайте коммит:

     ```
     git add git_clients.md
     git commit -m "Add third git client"
     ```

4. Восстановление файла из коммита 

   * Добавьте четвертый клиент Git в файл `git_clients.md` (создайте для него пункт в новой строке). После этого сохраните состояние файла:

     ```
     cp git_clients.md 4_restore/begin.txt
     ```

   * Восстановите состояние файла до коммита и сохраните состояние файла.

     Для отмены сделанных изменений в файле применяется команда `git restore`:

     ```
     git restore git_clients.md
     cp git_clients.md 4_restore/end.txt
     ```

5. Отмена коммита 

   * Выполните поиск в Интернете и узнайте об аналогах системы Git.

   * Откройте в текстовом редакторе файл `git_analogs.md` и последовательно добавьте в него два аналога системе Git. После каждого пункта сделайте коммит:

     ```
     git add git_analogs.md
     git commit -m "Add first git analog"
     git add git_analogs.md
     git commit -m "Add second git analog"
     ```

   * Сохраните историю изменений:

     ```
     git log > 5_reset/begin.txt
     ```

   * Отмените последний коммит и сохраните историю изменений снова.

     Для восстановления состояния репозитория на определенный коммит без изменения текущего состояния файлов используется команда `git reset --soft`:

     ```
     git reset --soft HEAD~1
     git log > 5_reset/end.txt
     ```

   * Выполните коммит снова:

     ```
     git add git_analogs.md
     git commit -m "Add second git analog again"
     ```

6. Работа со сторонним клиентом Git

   * Установите любой бесплатный клиент Git по вашему выбору.

   * Отройте текущий репозиторий в нем и сделайте скриншот с историей изменений.

   * Сохраните скриншот в каталоге `6_client`

7. Закомментировать все строки в файле `.gitignore`, выполнить коммит и отправить изменения на сервер для проверки:

   ```
   git add .
   git commit -m "Final commit"
   git push
   ```

## Ссылки с обзорами клиентов git

* https://git-scm.com/downloads/guis
* https://techrocks.ru/2020/04/24/best-git-gui-for-mac-linux-windows/
* https://itigic.com/ru/best-git-clients-with-graphical-interface-for-windows/
* https://tech-geek.ru/best-git-gui-clients-windows/
