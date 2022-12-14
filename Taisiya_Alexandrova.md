# Инструкция по работе с git 

## Подготовка 

1. **Регистрация на GitHub**. 
GitHub ­ это сервис для хранения репозиториев.  Репозиторий научного проекта будет находиться именно там, поэтому если у вас еще нет аккаунта на GitHub, вам необходимо пройти стандартную процедуру регистрации.

2. **Установить git** с официального сайта по инструкции: http://git­scm.com/downloads

3. Все команды git выполняются в **терминале** (командной строке).

4. **Настройка git**. Нам будет достаточно только задать имя и email командами:
    * _git config ­­global user.name "Ivan Ivanov"_
    * _git config ­­global user.email example@example.com_

## Базовые операции

* **Создание локальной копии главного репозитория**.

Давайте создадим в каталоге репозитория текстовый файл **_manual.md_**, содержащий строку текста **_"Some text"_**. Однако то, что файл появился в каталоге репозитория не означает, что git его уже отслеживает ­ нужно указать это явно командой: 

**_git add manual.md_**

Теперь наш файл находится под наблюдением git. Давайте сохраним изменения в
репозитории и сделаем первый коммит:

**_git commit -­m "Комментарий к коммиту на Eng языке"_**

**-­m** позволяет задать описание коммита. Описание обязательно, иначе коммит не будет выполнен.

* **Сохранение изменений файлов**. 

Добавим в файл **_manual.md_** еще одну строчку **_"Some more text"_** (не забудьте сохранить файл!). И снова закоммитим изменения. Однако если мы воспользуемся известной нам командой:

**_git commit -­m "more text added to first.txt"_**

Чтобы меньше запоминать, вам будет достаточно для всех коммитов пользоваться
командой именно такого вида.

**-­a** позволяет учесть изменения только в файлах, уже
находящихся под наблюдением git. А новые файлы перед коммитом необходимо
предварительно явно добавить командой **_git add_**.

**_git commit -a -­m "more text added to first.txt"_**

* **Проверить текущий статус репозитария** 

Используйте команду **_git status_**

![Status](.\Status.png)

* **Просмотреть историю проекта**
Используйте команду **_git log_**

![Log](.\Log.png)

* **Переход между коммитами**

Используйте команду **_git checkout номер коммита_**
Номера коммитов можно посмотреть посредством команды **_git log_**

* **Вернуться к актуальному состоянию и продолжить работу**

Используйте команду **_git checkout master_**

* **Просмотреть разницу между текущим файлом и закоммиченным файлом**

Используйте команду **_git diff_**

## Краткое содержание по работе с Git и языком Markdown

* Основные команды Git

✦ git init – инициализация локального репозитория

✦ git status – получить информацию от git о его текущем состоянии

✦ git add – добавить файл или файлы к следующему коммиту

✦ git commit -m “message” – создание коммита.

✦ git log – вывод на экран истории всех коммитов с их хеш-кодами

✦ git checkout – переход от одного коммита к другому

✦ git checkout master – вернуться к актуальному состоянию и продолжить работу

✦ git diff – увидеть разницу между текущим файлом и закоммиченным файлом


* Синтаксис языка Markdown

Справочник по Markdown от Microsoft:
https://docs.microsoft.com/ru-ru/contribute/markdown-reference

✦ # Заголовок – выделение заголовков. Количество символов “#” задаёт уровень заголовка (поддерживается 6 уровней).

✦ = или - – подчёркиванием этими символами (не менее 3 подряд) выделяют заголовки 
первого (“=”) и второго (“-”) уровней.

✦ ** Полужирное начертание** или __ Полужирное начертание__

✦ *Курсивное начертание* или _Курсивное начертание_

✦ ***Полужирное курсивное начертание***

✦ ~~Зачёркнутый текст~~

✦ * Строка – ненумерованные списки, символ “*” в начале строки

✦ 1, 2, 3 … – нумерованные списки

## Дополнительные источники по работе с Git и языком Markdown

* [Git для новичков (часть 1)](https://habr.com/ru/post/541258/)
* [Git для новичков (часть 2)](https://habr.com/ru/post/542616/)
* [Git для начинающих](https://ruseller.com/lessons.php?rub=28&id=2035)
* [Справочные материалы по Markdown](https://learn.microsoft.com/ru-ru/contribute/markdown-reference)
* [Использование ссылок в документации](https://learn.microsoft.com/ru-ru/contribute/how-to-write-links)

## Ветки

### 1. *Работа с Ветками*

Ветка в Git это подвижный указатель на один из коммитов. Обычно ветка указывает на последний коммит в цепочке коммитов. Ветка берет свое начало от какого-то одного коммита. Визуально это можно представить вот так.

![vetki](.\vetki.png)

Сделать новую ветку и переключиться на нее можно выполнив команду

*__git checkout –b имя_новой_ветки__*

Просто сделать ветку, не переключаясь на нее можно командой

*__git branch имя_новой_ветки__*

переключиться на ветку

*__git checkout –b имя_ветки__*

*Важно понимать, что ветка берет свое начало не от ветки, а от последнего коммита который находиться в той ветке, в которой вы находились*

Ветка обычно заканчивается специальным merge коммитом, который говорит, что ветку нужно объединить с какой-то другой веткой. В merge коммите содержатся две ссылки на два коммита которые объединяются в одну ветку.

![merge_commit](.\merge_commit.png)

После того, как ветка объединяется с другой веткой, все коммиты сделанные в ней, попадают в ветку с которой она была объединена. Так же важно понимать, что merge это не двунаправленная операция. Если смержить ветку задачи в мастер ветку, то в мастер ветке появится код, который находился в ветке задачи, а в ветке задачи не появиться новый код из мастер ветки. Если нужно что бы это произошло, нужно смержить мастер ветку в ветку задачи.
Что бы смержить одну ветку в другую нужно вначале переключиться на ту ветку, в которую вы хотите смержить.

Чтобы смержить одну ветку в другую нужно вначале переключиться на ту ветку, в которую вы хотите смержить

*__git checkout имя_ветки__*

Затем выполнить команду

*__git merge имя_ветки_которую_надо_смержить__*

### 2. *Конфликты при слиянии (merge) веток*

Конфликты возникают при мердже веток если в этих ветках одна и та же строка кода была изменена по-разному. Тогда получается, что Git не может сам решить какое из изменений нужно применить и он предлагает вручную решить эту ситуацию. Это замедляет работу с кодом в проекте. Избежать этого можно разными методами. Например, можно распределять задачи так, чтобы связанные задачи не выполнялись одновременно различными программистами.
Другой способ избежать этого, это договориться о каком-то конкретном стиле кода. Тогда программисты не будут менять форматирование кода и вероятность того, что они изменят одну и ту же строчку станет ниже.

Еще один хороший совет, который поможет вам избежать конфликтов при работе в команде, это вносить минимум изменений в код при решении задач. Чем меньше строчек вы поменяли, тем меньше вероятность что вы измените ту же самую строку что и другой программист в другой задаче.

После того, как в мастер ветке достигается состояние, которое можно считать стабильным оно отмечается тегом с версией этого состояния. Это и есть то что называют версией программы.
Делается это вот так

*__git tag -a v1.0__*

Теги удобны еще и тем, что можно легко переключиться на то состояние кода которое отмечено тегом. Делается это с помощью все той же команды

*__git checkout имя_тега__*

### 3. *Удаление веток*

Большинство веток в ваших репозиториях, скорее всего, будут короткоживущими: создали ветку, протестировали новую функцию, *слили ветку с основной* и удалили ее.

Как и всегда, когда речь доходит до удаления чего-либо, нужно быть очень *осторожными*. Когда вы удаляете ветку, все изменения, которые не были добавлены в коммит, будут утеряны. 

Итак, для удаления ветки используйте команды

* *__git branch -d имя_ветки__*

-d (delete) c этим ключем команда удалит вашу ветку. Ветка будет удалена только в том случае, если она полностью слита с одной из других веток. В противном случае, Git выдаст предупреждение, о том, что в ветке есть неслитые изменения, и не даст ее удалить.

* *__git branch -D имя_ветки__*

-D (Delete) этот ключ нужен, если вы хотите удалить ветку, игнорируя предупреждения Git. В отличие от -d, этот ключ удалит ветку в любом случае, даже если в ней есть изменения, которые вы можете потерять.

Большинство веток в ваших репозиториях, скорее всего, будут короткоживущими: создали ветку, протестировали новую функцию, *слили ветку с основной* и удалили ее.

Как и всегда, когда речь доходит до удаления чего-либо, нужно быть очень *осторожными*. Когда вы удаляете ветку, все изменения, которые не были добавлены в коммит, будут утеряны. 

Если вам нужно получить список определенного множества веток, то можно воспользоваться ключами. Одними из самых распространенных будут:

-r — при использовании этого ключа мы получим список удаленных веток,
-a — используя этот параметр, в выводе будут удаленные и локальные ветки.

В процессе разработки могут возникнуть ситуации, когда необходимо по-другому называть уже созданную ветку. Это может быть связано с разными причинами (например, разрабатываемый в данной версии функционал не соответствует названию). 

Чтобы переименовать ветку используйте команду

*__git branch -m новое_имя_ветки__*

Однако, здесь нужно быть аккуратными, чтобы не перегрузить проект ненужными ветками. Если запушить переименованную ветку, то на сервере появится ветка с новым именем, но и ветка со старым названием тоже останется. 

Чтобы избежать такой проблемы, *необходимо удалить ветку локально и на сервере*.

### Подробнее о работе с Ветками можно ознакомиться на ресурсах

* [Git на практике](https://habr.com/ru/post/342116/)
* [Работа с Git](https://smartiqa.ru/courses/git)
* [Работа с ветками в Git (git branch)](https://selectel.ru/blog/tutorials/how-to-work-with-branches-in-git-git-branch/)

## Работа с Remote (удаленными) репозиториями

**Удаленный (иногда говорят "внешний") репозиторий** – это версии вашего проекта, сохраненные на удаленном сервере. Доступ к репозиторию на таком сервере может осуществляться по интернету или по локальной сети.
Удаленный репозиторий – полноценный репозиторий, ничем не отличающийся от локального. У удаленного репозитория есть собственные ветки, своя история коммитов и так далее.

Удаленный репозиторий – полноценный репозиторий, ничем не отличающийся от локального. Если мы подключим удаленный репозиторий к своему локальному, то у нас появятся копии всех ссылочных объектов удаленного репозитория.

**Примечание**

*__Удаленный репозиторий может находиться на вашем локальном компьютере.__*
Вполне возможно, что удалённый репозиторий будет находиться на том же компьютере, на котором работаете вы. Слово «удалённый» не означает, что репозиторий обязательно должен быть где-то в сети или Интернет, а значит только — где-то ещё. Работа с таким удалённым репозиторием подразумевает выполнение стандартных операций отправки и получения, как и с любым другим удалённым репозиторием.

### Добавление удаленного репозитория (clone) к существующему локальному

Чтобы добавить Для этого в Git есть команда:

*__git clone <ссылка на удаленный репозиторий>__*

Мы работаем с [GitHub] (https://github.com), поэтому эту **Ссылку** на удаленный репозиторий взять, нажав на большую зеленую кнопку *Code* на странице репозитория на GitHub.

![Code button](.\code_button.png)

### Отправка изменений в удаленный репозиторий (push)

Когда вы хотите поделиться своими наработками, вам необходимо отправить их в удалённый репозиторий. Команда для этого действия простая: 

*__git push <branch-name>__*

Git покажет ошибку и предложит правильную (полноценную) для ввода команду. Копируем и отправляем эту команду.

**Примечание**: При первом запуске команды *push* потребуется авторизация на github

Если же Вам необходимо подятнуть изменения, которые вы делали в удаленном репозитории с другого устройства (или на github), в локальную копию этого репозитория, необходимо использовать команду:

*__git pull [имя удаленного репозитория]__*

### GitHub. Работа с репозиторием, Fork и pull request

#### Создание репозитория на GitHub
Прежде всего вам необходимо зарегистрироваться на GitHub, но это довольно тривиальный процесс, так что его мы здесь опустим. После регистрации вы попадете на главную страницу. На ней будут отображаться действия людей, на которых вы подписались и обновления в репозиториях, которые вы добавили в избранное.

Чтобы создать свой репозиторий, нажмите на зеленую кнопку New, как показано на рисунке.

![New rep](.\new_rep.png)

Перед вами откроется страница создания репозитория. Давайте разберем, что за поля нам предлагают заполнить.

1. Итак, первое поле **Repository name** – имя репозитория. Здесь все просто, вам нужно придумать имя, которое будет отображаться на странице вашего репозитория. Здесь нет никаких ограничений, но старайтесь давать как можно более содержательные имена своим репозиториям.
2. Второе поле – **Description** – описание. Его заполнять необязательно. Но другим пользователям, которые попали на страницу вашего репозитория, будет проще понять, что перед ними, если вы заполните графу описания.
Затем вы можете выбрать, будет ли репозиторий открытым, то есть доступным абсолютно всем пользователям GitHub, или закрытым, то есть доступным только вам и людям, которым вы предоставите доступ.
Последние три поля предлагают нам добавить, соответственно, **README-файл**, **.gitignore** файл и выбрать лицензию для нашего проекта.

После заполнения полей страница выглядит примерно так.

![New rep 2](.\new_rep_2.png)

#### Создание форка репозитория на GitHub. Pull request.

Итак, одной из самых важных частей GitHub является создание форков.

Fork (англ. fork – вилка) – точная копия репозитория, но в вашем аккаунте. Форки нужны, чтобы вносить свои изменения в проект, к репозиторию которого у вас нет прямого доступа.

Pull-request (англ. pull-request – запрос pull) – функция GitHub, позволяющая попросить владельца репозитория, от которого мы сделали форк, загрузить наши изменения обратно в свой репозиторий.

Если коротко, форки и пулл-реквесты нужны, чтобы любой пользователь мог внести свой вклад в любой открытый проект, репозиторий которого есть на GitHub. Кроме того, перед тем как влить ваши изменения в основной репозиторий, ответственные обязательно проверят ваш код на наличие ошибок и уязвимостей. Таким образом, даже если ваши изменения не примут, вы получите первоклассный **code-review** с указанием всех неточностей.

1. Для начала зайдем на страницу репозитория проекта. Нажимаем на кнопку Fork, как показано на картинке. После этого Git создаст точную копию этого репозитория в вашем аккаунте.

![Fork](.\Fork.png)

![Fork 2](.\Fork_2.png)

2. Клонируем репозиторий к себе на компьютер командой **git clone**. Создадим файл **README.md** с описанием проекта, чтобы другим пользователям было понятно, в чем отличие этой реализации от остальных.

3. Сделаем коммит и выполним **git push**, чтобы загрузить наши изменения в удаленный репозиторий.

4. Теперь GitHub подсказывает нам, что наша ветка опережает ветку исходного репозитория на один коммит и предлагает сделать пулл-реквест.

![Push](.\Push.png)

5. Нажимаем на кнопку **Compare** на подсказке GitHub, либо переходим на вкладку **Pull Requests** и нажимаем **New pull request**.

![Pull](.\Pull.png)

6. Перед нами откроется страница создания пулл-реквеста.

![Pull_request](.\Pull_request.png)

Здесь мы можем просмотреть внесенные изменения и выбрать две ветки: одну в исходном репозитории, на нее будут залиты наши изменения, вторую – в нашем репозитории, с нее будут скачаны изменения. Как только мы выбрали ветки и убедились, что не внесли никаких лишних изменений, нажимаем кнопку **Create pull request**.

7. Теперь мы попадаем на страницу описания наших изменений.

![Pull_request_2](.\Pull_request_2.png)

Здесь необходимо описать, что за изменения вы внесли и почему они были необходимы. Сообщение, которое оставили мы, видно на картинке. Оно отражает суть и необходимость внесенных изменений. Как только мы закончили с описанием, можно нажимать кнопку **Create pull request**.

8. Теперь мы попадаем на страницу уже созданного пулл-реквеста в изначальном репозитоии. В нашем случае он выглядит так.

![Pull_request_3](.\Pull_request_3.png)

Именно так будет выглядеть наш пулл-реквест и для владельца репозитория. На этой странице он сможет писать комментарии, указывая на ошибки или задавая вопросы. После того, как владелец репозитория просмотрит наши изменения и убедится, что они не имеют вредоносный характер, он сможет принять наш пулл-реквест. Тогда все изменения, добавленные в этот пулл-реквест нами, будут залиты в исходный репозиторий.