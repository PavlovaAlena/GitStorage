## **Оглавление**
#### **Основные команды Git**
1. [init](#init)
2. [status](#status)
3. [add и commit](#add_commit)
4. [log](#log)
5. [checkout](#checkout)
6. [diff](#diff)
7. [gitignore](#gitignore)
8. [rm](#rm)
9. [branch](#branch)
10. [merge](#merge)
#### **Работа с GitHub**
11. [proxy](#proxy)
12. [prremote и clone](#remote_clone)
13. [pull и push](#pull_push) 
14. [fork и pull](#fork_pull)

**Git** — это набор консольных утилит, которые отслеживают и фиксируют изменения в файлах (чаще всего речь идет об исходном коде программ, но можно использовать его для любых файлов).
Для освоения можно воспользоваться:
* [интерактивным учебником по Git](https://learngitbranching.js.org/?locale=ru_RU "Для перехода нажмите на ссылку"), который создан, чтобы помочь новичкам постичь работу с git.

или 

* краткой инструкцией по основным командам, представленной ниже.

## ***Основные команды Git***
## 1. git init — создание репозитория <div id="init"/>
___
 Команда создает в директории пустой репозиторий в виде директории .git, где и будет в дальнейшем храниться вся информация. Вводится: 
 > git init

____
***При первом использовании Git необходимо представиться.  Для этого нужно ввести в терминале 2 команды:***

*git config --global user.name «Ваше имя английскими буквами»**

*git config --global user.email ваша почта@example.com*
___

## 2. git status — состояние проекта <div id="status"/>
___
 Она выводит информацию обо всех изменениях, внесенных в дерево директорий проекта по сравнению с последним коммитом рабочей ветки; отдельно выводятся внесенные в индекс и неиндексированные файлы. Т.е. получает информацию от git о его текущем состоянии. Вводится: 
 > git init

## 3. git add и git commit — индексация изменений и создание коммита <div id="add_commit"/>
___

* **git add** позволяет внести в индекс — временное хранилище — изменения, которые затем войдут в коммит
> git add .\file_name - добавляет указанный файл

> git add . - добавляет все файлы репозитория

* **git commit** создание коммита. Если индекс не пустой, то на его основе будет совершен коммит.
> git commit -m "text" -  создает коммит из командной строки

## 4. git log — информация о коммитах в целом <div id="log"/>
___
Dывод на экран истории всех коммитов с их хеш-кодами: информацию об истории коммитов; коммитах, изменивших отдельный файл; коммитах за определенный отрезок времени и так далее. Вводится: 
 > git log - короткая справка по всем коммитам, коснувшимся активной в настоящий момент ветки (журнал)

![Пример log](/GitLog.png "Пример работы комманды log")

Если коммитов много, то для просмотра используют пробел, стрелки или энтер. Для возврата к коммандной строке, необходимо нажать на клавиатуре "q".
 > git log --oneline - компактный журнал: идентификатор и коммит

![Пример log](/GitLogOL.png "Пример работы комманды log")

Для вывода дерева зависимостей для всех коммитов используется:
> git log --graph

## 5. git checkout — переключение между ветками, извлечение файлов <div id="checkout"/>
___
Команда позволяет переключаться между коммитами веток, как между удаленными, так и между локальными ветками. Вводится: 
 > git checkout <идентификатор_коммита> - переключение на ветку

 > git checkout master - возврат к активной ветке (актуальному состоянию и продолжение работы)

 > git checkout -b <имя_ветки> - создание новой ветки и сразу же выполняется переключение на нее.

## 6. git diff — отличия между деревьями проекта, коммитами и т.д. <div id="diff"/>
___
Команда определяет изменения между объектами в проекте - деревьями (файлов и
директорий): 
 > git diff - изменения, не внесенные в индекс

 > git diff --cached - изменения, внесенные в индекс

 ## 7. .gitignore - файл для отслеживания игнорируемых файлов <div id="gitignore"/>
___
 Игнорируемые файлы отслеживаются в специальном файле .gitignore, который регистрируется в корневом каталоге репозитория. В Git нет специальной команды для указания игнорируемых файлов: вместо этого необходимо вручную отредактировать файл .gitignore, чтобы указать в нем новые файлы, которые должны быть проигнорированы. Файлы .gitignore содержат шаблоны (имена файлов), которые сопоставляются с именами файлов в репозитории для определения необходимости игнорировать эти файлы.

 ## 8. git rm - удаление файла из рабочей копии и индекса / только из индекса <div id="rm"/>
 ___
 Основное назначение git rm — это удаление отслеживаемых файлов из раздела проиндексированных файлов. Кроме того, с помощью **git rm** можно удалить файлы одновременно из раздела проиндексированных файлов и рабочего каталога. Удалить с ее помощью файл только из рабочего каталога нельзя.
 > git rm <file_name> - удаляет файл из рабочей копии и индекса. Можно указать один файл, несколько файлов через пробел (file1 file2 file3) или шаблон подстановки (~./directory/*).
 
> git rm --cashed <file_name> - удаляет файл из индекса и перемещает его в категорию Неотслеживаемые.
>>Что бы удалить потом файл из рабочего каталога, нужно воспользоваться командой **rm <file_name>** (без использования git)

 ## 9. git branch - работа с ветвлением <div id="branch"/>
___
Ветка – это последовательность коммитов. Для начала работы с новой веткой нужно выполнить два действия:
1. Создать ветку с помощью команды **git branch**
2. Переключиться на свежесозданную ветку с помощью команды **git checkout <name_branch>**
> git branch - показывает список веток (* - текущая)

![Пример branch](/Gitbranch.png "Пример работы комманды branch")

> git branch <name_branch> - cоздает новую ветку

> git branch -d <name_branch> - ветка будет удалена, но только в том случае, если она полностью слита с одной из других веток. В противном случае, Git выдаст предупреждение, о том, что в ветке есть неслитые изменения, и не даст ее удалить

>git branch -D <name_branch> - ветка будет удалена, игнорируя предупреждения Git. В отличие от -d, ключ -D удалит ветку в любом случае, даже если в ней есть изменения, которые можно потерять.

 ## 10. git merge - объединяет несколько последовательностей коммитов в общую историю <div id="merge"/>
___
 Команда выполняет слияние отдельных направлений разработки, созданных с помощью команды **git branch**, в единую ветку. cлияние выполняется в текущую ветку, в то время как целевая ветка остается без изменений.
 > git merge <имя_ветки> - объединяет несколько последовательностей коммитов в общую историю, где <название ветки> — название ветки, которая будет объединена с принимающей

***Ускоренное слияние*** происходит, когда последний коммит текущей ветки является прямым продолжением целевой ветки. В этом случае для объединения истории Git не выполняет полноценное слияние, а просто переносит указатель текущей ветки в конец целевой ветки.

***Конфликт*** возникает при попытке объединить ветки, в которых изменена одна и та же часть того же файла и Git не сможет сделать выбор между версиями. В таком случае операция останавливается прямо перед созданием коммита слияния, чтобы пользователь вручную разрешил конфликты. Конфликт возникает, когда в двух ветках была изменена одна и та же строка в файле или когда некий файл удален в одной ветке и отредактирован в другой.

 Разрешение конфликтов при слиянии проходит по привычной схеме «редактирование — индексирование — коммит».

![Пример merge](/GitMergeConf.png "Пример работы комманды merge")

## ***Работа с GitHub***
## 11. proxy - работа через прокси-сервер <div id="proxy"/>
___
Для работы через proxy необходимо в git внести соответствующие адрес и порт.

**Незащищенный прокси (http)**
>git config --global http.proxy http://proxy.company.com:port
>>**И отключить его:**
>>git config --global --unset-all http.proxy

**Защищенный прокси (https)**
>git config --global https.proxy https://proxy.company.com:port
>>**И отключить его:**
>>git config --global --unset-all https.proxy

Или прописать настройк напрямую в файле .gitconfig, который лежит в домашней директории пользователя C:\Users\Имя_Пользователя

>[http]  
>  	proxy = proxyfg.argos-group.ru:3128  
>[https]  
>	proxy = https://proxyfg.argos-group.ru:3128

Если через proxy нужно разово получить с GitHub, то можно воспользоваться:
>git -c "http.proxy=proxy.company.com:port" clone https://github.com/PavlovaAlena/version_control_lection_3.git

## 12. remote и clone - подключение(получение) удаленных репозиторий <div id="remote_clone"/>
Удаленный репозиторий – полноценный репозиторий, ничем не отличающийся от локального, т.е. версии проекта, сохраненные на удаленном сервере. Доступ к репозиторию на таком сервере может осуществляться по интернету или по локальной сети.

> git remote add <название_удаленного_репозитория> <ссылка_на_удаленный_репозиторий> - подключает удаленный репозиторий к локальному под переданным именем.  
>>*Название удаленного репозитория* - любое придуманное имя, по которому впоследствии, при работе с этим удаленным репозиторием, нужно будет обращаться.  
*Ссылка на удаленный репозиторий* - ее можно взять, нажав на большую зеленую кнопку Code на странице репозитория на GitHub.

> git remote remove <название_удаленного_репозитория> - отключает переданный удаленный репозиторий от локального. 

> git clone <ссылка_на_удаленный_репозиторий> - клонирует переданный репозиторий на компьютер.
>>*Ссылка на удаленный репозиторий* - ее можно взять, нажав на большую зеленую кнопку Code на странице репозитория на GitHub.  
>>1. В директории, откуда запустили команду **git clone**, создается директория с именем репозитория (будет создана папка)
>>2. В созданную директорию копируется репозиторий, все его ветки и коммиты.
В новосозданный локальный репозиторий добавляется удаленный репозиторий с именем origin и ссылкой, которую передавали в **git clone**.  
>>На этом процесс клонирования заканчивается.

## 13. pull и push - синхронизация с GitHub <div id="pull_push"/>
> git pull [ключи] [имя_удаленного_репозитория] - получает изменения из переданного удаленного репозитория и обновляет рабочую копию в соответствии с удаленным репозиторием. Используется для синхронизации локальной рабочей копии и всех ссылочных объектов с удаленным репозиторием.

>git push [ключи] [имя_удаленного_репозитория] [имя_ветки] - загружает изменения в удаленный репозиторий. 
>> git push --all [имя_удаленного_репозитория] - пушит все имеющиеся ветки

## 14. fork и pull-request - работа с открытыми проектами на GitHub <div id="fork_pull"/>
**Fork (форк)** – точная копия репозитория открытого проекта, но в своем аккаунте. Форки нужны, чтобы вносить свои изменения в проект, к репозиторию которого нет прямого доступа.  
**Pull-request (пулл-реквест)** – функция GitHub, позволяющая попросить владельца репозитория, от которого cделан форк, загрузить изменения обратно в репозиторий.

Порядок работы в данном случае:
1. Сделать **fork** интересующего репозитория на GitHub
2. Сделать **git clone**
3. Создать новую ветку, в которой прописать изменения
4. Сделать **git add** и **git commit**
5. Сделать **git push** своей ветки
6. Сделать **Pull-request**