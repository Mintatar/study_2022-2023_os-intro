---
## Front matter
title: "Отчет по лабораторной работе"
subtitle: "Лабораторная работа 11"
author: "Мурзаев Замир Зейнадинович"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Цель - изучить основы программирования в оболочке ОС UNIX, научиться писать более сложные командные файлы с использованием логических управляющих конструкций и циклов.

# Задание

1. Используя команды getopts grep, написать командный файл, который анализирует
командную строку с ключами:
– -iinputfile — прочитать данные из указанного файла;
– -ooutputfile — вывести данные в указанный файл;
– -pшаблон — указать шаблон для поиска;
– -C — различать большие и малые буквы;
– -n — выдавать номера строк.
а затем ищет в указанном файле нужные строки, определяемые ключом -p.
2. Написать на языке Си программу, которая вводит число и определяет, является ли оно
больше нуля, меньше нуля или равно нулю. Затем программа завершается с помощью
функции exit(n), передавая информацию в о коде завершения в оболочку. Команд-
ный файл должен вызывать эту программу и, проанализировав с помощью команды
$?, выдать сообщение о том, какое число было введено.
3. Написать командный файл, создающий указанное число файлов, пронумерованных
последовательно от 1 до 𝑁 (например 1.tmp, 2.tmp, 3.tmp,4.tmp и т.д.). Число файлов,
которые необходимо создать, передаётся в аргументы командной строки. Этот же ко-
мандный файл должен уметь удалять все созданные им файлы (если они существуют).
4. Написать командный файл, который с помощью команды tar запаковывает в архив
все файлы в указанной директории. Модифицировать его так, чтобы запаковывались
только те файлы, которые были изменены менее недели тому назад (использовать
команду find).

# Выполнение лабораторной работы

1)Пишем программу, которая анализирует командную строку, а затем ищет нужные строки (рис. @fig:001).

![Командный файл](image/1.png){#fig:001 width=90%}

2)Пишем код на языке C (рис. @fig:002) и командный файл, который взаимодействует с ним (рис. @fig:003).

![файл .c](image/2.png){#fig:002 width=90%}

![Командный файл](image/3.png){#fig:003 width=90%}

3)Пишем файл, который генерирует определенное количество файлов (рис. @fig:004).

![Командный файл](image/4.png){#fig:004 width=90%}

4)Пишем файл, который запаковывает в архив все файлы в директории (рис. @fig:005).

![Командный файл](image/5.png){#fig:005 width=90%}

#Ответы на вопросы


    Каково предназначение команды getopts?

Ответ: команда анализирует аргументы, переданные скрипту.

    Какое отношение метасимволы имеют к генерации имён файлов?

Ответ: метасимволы позволяют создавать файлы, используя шаблоны.

    Какие операторы управления действиями вы знаете?

Ответ: && и ||.

    Какие операторы используются для прерывания цикла?

Ответ: break, continue.

    Для чего нужны команды false и true?

Ответ: false всегда возвращает код завершения, не равный нулю (т. е. ложь). Команда true выполняет обратное действие.

    Что означает строка if test -f man$s/$i.$s, встреченная в командном файле?

Ответ: це проверка условия на наличие файла с шаблоном имени if test -f man$s/$i.$s.

    Объясните различия между конструкциями while и until.

Ответ: при замене в операторе цикла while служебного слова while на until условие, при выполнении которого осуществляется выход из цикла, меняется на противоположное. В остальном оператор цикла while и оператор цикла until идентичны.

# Выводы

Изучены основы программирования в оболочке ОС UNIX и приобретены навыки по написанию более сложных командных файлов с использованием логических управляющих конструкций и циклов.

# Список литературы{.unnumbered}

::: {#refs}
:::
