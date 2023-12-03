# The Bandit wargame v1.0

Linux basic bash scripting and system research.

## Contents

- [The Bandit wargame v1.0](#the-bandit-wargame-v10)
  - [Contents](#contents)
  - [Chapter I](#chapter-i)
  - [Chapter II](#chapter-ii)
    - [Bash](#bash)
    - [Shell](#shell)
  - [Chapter III](#chapter-iii)
  - [Part 1. Проба пера](#part-1-проба-пера)
  - [Part 2. Исследование системы](#part-2-исследование-системы)
  - [Part 3. Визуальное оформление вывода для скрипта исследования системы](#part-3-визуальное-оформление-вывода-для-скрипта-исследования-системы)
  - [Part 4. Конфигурирование визуального оформления вывода для скрипта исследования системы](#part-4-конфигурирование-визуального-оформления-вывода-для-скрипта-исследования-системы)
  - [Part 5. Исследование файловой системы](#part-5-исследование-файловой-системы)
  - [Chapter IV](#chapter-iv)

## Chapter I

![The Bandit wargame v1.0](kandinsky-download-1701599552895_bandit.png)

Планета Земля, США, штат Калифорния, город San Francisco, уютная кальянная "Code Clouds", настоящее время.

Вечер был наполнен облаками табачного дыма и тихим плеском воды в кальяне. Майк, опытный программист, пригласил своего друга Дэна в это уютное место.

Ну что, Дэн, давно не виделись. Ты не думал, что я позвал тебя просто посидеть и насладиться ароматом табака в кальяне? - сказал Майк с улыбкой.
Дэн посмотрел на него с удивлением: 

`-`  От тебя никогда не скрыть, Майк! Что у тебя на уме?

Хватит мне льстить, дружище. Я заметил, что ты недавно взялся за решение задач на OverTheWire. Вот и я обратился к тебе, как к опытному хакеру.
Дэн улыбнулся: 

`-` Да, я решил погрузиться в мир безопасности и начать с задач на площадке Bandit. Но тут же возникли проблемы - оказалось, что у них там основной инструмент - Linux, а я привык к Windows.

И вот я пришел к тебе, такому опытному в области Linux и администрирования, чтобы ты мне помог. Ты готов к новому вызову?
Дэн задумался, а затем ответил: 

`-` Конечно, Майк! Доставай свой ноутбук, давай устроим настоящий кибербез в Code Clouds. Смешаем хакинг с ароматом табака и посмотрим, что получится.

Пока Дэн доставал свой ноутбук, Майк решил рассказать ему небольшую историю:

Знаешь, когда-то и я сталкивался с подобным вызовом. Был как ты, но с той разницей, что в клубе была джазовая композиция, а сейчас перед нами - мир Linux и OverTheWire. Впереди нас ждут интересные задачи и увлекательные открытия!

## Chapter II

### Bash

>Bash is the shell, or command language interpreter, for the GNU operating system.
>
>The name is an acronym for the ‘Bourne-Again SHell’, a pun on Stephen Bourne, the author of the direct ancestor of the current Unix shell sh, which appeared in the Seventh Edition Bell Labs Research version of Unix.
>
>Bash is largely compatible with sh and incorporates useful features from the Korn shell ksh and the C shell csh. It is intended to be a conformant implementation of the IEEE POSIX Shell and Tools portion of the IEEE POSIX specification (IEEE Standard 1003.1). It offers functional improvements over sh for both interactive and programming use.
>
>While the GNU operating system provides other shells, including a version of csh, Bash is the default shell. Like other GNU software, Bash is quite portable. It currently runs on nearly every version of Unix and a few other operating systems - independently-supported ports exist for MS-DOS, OS/2, and Windows platforms.

### Shell

>At its base, a shell is simply a macro processor that executes commands.
>
>A Unix shell is both a command interpreter and a programming language. As a command interpreter, the shell provides the user interface to the rich set of GNU utilities. Files containing commands can be created, and become commands themselves. These new commands have the same status as system commands, allowing users or groups to establish custom environments to automate their common tasks.
>
>Shells may be used interactively or non-interactively. In interactive mode, they accept input typed from the keyboard. When executing non-interactively, shells execute commands read from a file.
>
>A shell allows execution of GNU commands, both synchronously and asynchronously.
>
>While executing commands is essential, most of the power (and complexity) of shells is due to their embedded programming languages. Like any high-level language, the shell provides variables, flow control constructs, quoting, and functions.
>
>Shells offer features geared specifically for interactive use rather than to augment the programming language. These interactive features include job control, command line editing, command history and aliases.

Под вырезками из статей, в ящике Майка, лежала папка с подписью "materials". Заглянув в неё, Джон обнаружил несколько листов с описанием возможностей bash-скриптов.

## Chapter III
Игра Bandit предназначена для абсолютных новичков. Она научит основам, необходимым для игры в другие игры на площадке OverTheWire.

# Примечание для новичков

Эта игра, как и большинство других, организована по уровням. Вы начинаете с уровня 0 и пытаетесь его "пройти" или "завершить". Завершение уровня приводит к информации о том, как начать следующий уровень. Страницы на веб-сайте [OverTheWire](https://overthewire.org/wargames/bandit/)
для "Уровня X" содержат информацию о том, как начать уровень X с предыдущего уровня. Например, страница для Уровня 1 содержит информацию о том, как получить доступ с Уровня 0 на Уровень 1. Все уровни в этой игре имеют свою страницу на веб-сайте, и все они расположены сбоку страницы.

Вы столкнетесь с множеством ситуаций, в которых вы не знаете, что вам делать. Не паникуйте! Не сдавайтесь! Цель этой игры - научить вас основам. Частью изучения основ является чтение большого количества новой информации. 

Есть несколько вещей, которые вы можете попробовать, когда не уверены, как продолжить:

Во-первых, если вы знаете команду, но не знаете, как ее использовать, попробуйте мануал (страница man), введя man <команда>. Например, man ls, чтобы узнать о команде "ls". У команды "man" также есть справка, попробуйте ее! При использовании man нажмите q для выхода (вы также можете использовать / и n и N для поиска).
Во-вторых, если нет страницы man, команда может быть встроенной в оболочку. В этом случае используйте команду "help <X>". Например, help cd.
Кроме того, ваш любимый поисковик - ваш друг. Научитесь им пользоваться! Рекомендую Google.
Наконец, если у вас все еще что-то не получается, вы можете присоединиться к нам через чат.
Вы готовы начать! Начните с Уровня 0, ссылка находится слева от этой страницы. Удачи!

## Part 1. Проба пера

Перед тем, как приступать к помощи коллеге, Джон решил проверить свои знания на совсем простом задании.

**== Задание ==**
Пароль для следующего уровня хранится в файле с именем readme, расположенном в домашнем каталоге. Используйте этот пароль для входа в bandit1 с использованием SSH. Когда вы найдете пароль для уровня, используйте SSH (на порту 2220), чтобы войти в этот уровень и продолжить игру.


Первый уровень довольно прост - ваша задача найти 'флаг', символизирующий успешное завершение задания.

Так, мы вводим 
```console
foo@bar:~$ ssh bandit.labs.overthewire.org -p 2220 -l bandit0

```
чтобы подключиться к нашему первому уровню. Просто введите пароль 'bandit0', и мы внутри.
Как видите, привычные команды Linux, такие как 'ls', 'cd' и 'cat', будут вашими верными спутниками на этом пути.

## Part 2. Криптографическая Загадка: имя файла - ключ к следующему уровню.

Теперь Джон уверен в том, что готов продолжать выполнять задания.

**== Задание ==**


Пароль для следующего уровня хранится в файле с названием -, расположенном в домашнем каталоге.


## Part 3. Загадочные Пробелы: Отыщите Пароль в файле с пробелами в названии

**== Задание ==**


Пароль для следующего уровня хранится в файле домашнего каталога, в названии которого содержатся пробелы.


## Part 4. Тайный Секрет inhere: Раскрой пароль в скрытом файле


**== Задание ==**

Пароль для следующего уровня хранится в скрытом файле в каталоге inhere.

## Part 5. Загадка Читаемости: Человек в поисках человекочитаемого пароля


**== Задание ==**


Пароль для следующего уровня хранится в единственном читаемом человеком файле в каталоге inhere. Совет: если ваш терминал испорчен, попробуйте команду "reset".


## Chapter IV

Джон доделал всё, что хотел. Всё-таки пришлось задержаться немного дольше, чем обычно, но это того стоило.
Он собирал вещи и, по пути к выходу из офиса, заглянул в комнату, в которой ранее слышал своего коллегу.

`-` Привет, я зайду? -- Джон постучался в дверь.

`-` Да... секунду. Не думал, что тут есть кто-то ещё в такое время.

Дверь открылась и, после недолгой беседы, Джон передал неопытному сисадмину флешку со скриптами.
Они уже попрощались и Джон собирался уходить, но тут он вспомнил одну важную деталь.

`-` Совсем забыл. Я Джон кстати, а тебя как звать то?

`-` Себастьян.
