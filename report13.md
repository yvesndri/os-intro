---
# Front matter
lang: ru-RU
title: "отчёта по лабораторной работе 13"
subtitle: " "
author: "Ндри Ив Алла Ролан"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---





## Цель работы
Познакомиться с операционной системой Linux. Получить практические навыки работы с редактором Emacs.

## Выполнение работы.
1  1	Осуществили вход в систему, создали текстовый документ, затем перешли в него. Написали командный файл, реализующий упрощённый механизм семафоров. Командный файл в течение некоторого времени t1 дожидается освобождения ресурса, выдавая об этом сообщение, а дождавшись его освобождения, использует его в течение некоторого времени t2<>t1, также выдавая информацию о том, что ресурс используется соответствующим командным файлом (процессом). Запустили командный файл в одном виртуальном терминале в фоновом режиме, перенаправив его вывод в другой, в котором также запущен этот файл, но не фоновом, а в привилегированном режиме. Доработали программу так, чтобы имелась возможность взаимодействия трёх и более процессов.  
(рис. -@fig:001) 
(рис. -@fig:002) 

![1](image/1.PNG) { # fig:001 width=70%} 
![2](image/2.PNG) { # fig:002 width=70%} 
 
 
2	C помощью командного файла реализуем команды man. Изучим содержимое каталога usr/share/man/man1. Каждый архив можно открыть при помощи команды less. Командный файл получает в виде аргументы командной строки название команды и и виде результат выдает справку.
(рис. -@fig:003)
(рис. -@fig:004)

![3](image/3.PNG) { # fig:003 width=70%}
![4](image/4.PNG) { # fig:004 width=70%}  

3.3	Используя встроенную переменную $RANDOM напишем командный файл, генерирующий случайную последовательность цифр.
(рис. -@fig:005)
(рис. -@fig:006)

 ![5](image/5.PNG) { # fig:005 width=70%} 
 ![6](image/6.PNG) { # fig:006 width=70%} 


## Вывод

Мы изучили основы программирования в оболочке ОС UNIX. Научились писать более сложные командные файлы, с использованием логических управляющих конструкций и циклов.

## Ответы на контрольные вопросы

1) Нужно поставить пробелы после [ и до ].
2) С помощью знака >.
3 )seq — Утилита, выводязая последовательность целых чисел с шагом, заданным пользователем. Так же можно реализовать с помощью утилиты jot.
4) 3
5) В zsh можно настроить отдельные сочетания клавиш так, как вам нравится. Использование  истории команд в zsh ничем особенным не отличается от bash.
Zsh очень удобен для повседневной работы и делает добрую половину рутины за вас. Но стоит обратить внимание на различия между этими двумя оболочками. Например, в zsh после for обязательно вставлять пробел, нумерация массивов в zsh начинается с 1, чего совершенно невозможно понять.
Так, если вы используете shell для повседневной работы, исключающей написание скриптов, используйте zsh. Если вам часто приходится писать свои скрипты, только bash! Впрочем, можно комбинировать.
6) Верно.
7) Bash является языком программирования очень высокого уровня. При должном навыке программиста, он может работать быстрее, чем Си. Однако его сложностью является то, что нужно следовать строгим правилам синтаксиса при написании программы.
