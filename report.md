---
# Front matter
lang: ru-RU
title: "отчёта по лабораторной работе 9"
subtitle: " т"
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
Познакомиться с операционной системой Linux. Получить практические навыки работы с редактором vi, установленным по умолчанию практически во всех дистрибутивах.

## Выполнение работы.
1   Ознакомились с теоретическим материалом.
 Ознакомились с редактором vi.
2 Упражнения по vi:

1 Создаю каталог с именем ~/work/os/lab06 (рис. -@fig:001)

![1](image/1.PNG) { # fig:001 width=70%} 
 
2 Перехожу во вновь созданный каталог.(рис. -@fig:002)

 ![2](image/2.PNG) { # fig:002 width=70%} 

3 Вызываю vi и создаю файл hello.sh vi hello.sh. (рис. -@fig:003)

 ![3](image/3.PNG) { # fig:003 width=70%} 

4 Нажимаю клавишу «i» и ввожу следующий текст:(рис. -@fig:004)

 ![4](image/4.PNG) { # fig:004 width=70%} 
 #!/bin/bash
HELL=Hello
function hello {
LOCAL HELLO=World
echo $HELLO
}
echo $HELLO
hello


5	Нажимаю клавишу «Esc» для перехода в командный режим после завершения ввода текста.(рис. -@fig:005)

![5](image/5.PNG) { # fig:005 width=70%} 

6	Нажимаю «:» для перехода в режим последней строки и внизу моего экрана появдяется приглашение в виде двоеточия. (рис. -@fig:006)

 ![6](image/6.PNG) { # fig:006 width=70%} 

7	Нажимаю «w» и «q», а затем нажимаю клавишу «Enter» для сохранения нашего текста и завершения работы.(рис. -@fig:007)

 ![7](image/7.PNG) { # fig:007 width=70%} 

8	Делаю файл исполняемым, вызвав команду «chmod +x hello.sh».(рис. -@fig:008)

 ![8](image/8.PNG)  { # fig:008 width=70%}  </br></br>
Задание 2. Редактирование существующего файла
1.	Вызываю vi на редактирование файла, команда: «vi ~/work/os/lab06/hello.sh».(рис. -@fig:009)

 ![9](image/9.PNG)  { # fig:009 width=70%} 
2.	Устанавливаю курсор в конец слова HELL второй строки. (рис. -@fig:0010)

	 ![10](image/10.PNG) { # fig;0010 width=70%} 
3 Перехожу в режим вставки и заменяю на HELLO. Нажимаю «Esc» для возврата в командный режим.(рис. -@fig:0011)
 ![11](image/11.PNG) { # fig:0011 width=70%} 
4	Устанавливаю курсор на четвертую строку и стерли слово LOCAL. (рис. -@fig:0012)

 ![12](image/12.PNG) { # fig:0012 width=70%} 
 
5	Перехожу в режим вставки и набрали: «local»; нажимаю «Esc» для возврата в командный режим.(рис. -@fig:0013)

 ![13](image/13.PNG) { # fig:0013 width=70%} 
 
6	Устанавливаю курсор на последней строке файла. Вставляю после неё строку, содержащую «echo $HELLO». (рис. -@fig:0014)

 ![14](image/14.PNG) { # fig:0014 width=70%} 
7	Нажимаю «Esc» для перехода в командный режим.

8	Удаляю последнюю строку. (рис. -@fig:0015)

  ![15](image/15.PNG) { # fig:0015 width=70%} 
9	 Ввожу команду отмены изменений «u» для отмены последней команды.(рис. -@fig:0016)

  ![16](image/16.PNG) { # fig:0016 width=70%} 
  
10 Ввожу символ «:» для перехода в режим последней строки. Записываю произведённые изменения и выхожу из vi.(рис. -@fig:0017) 

  ![17](image/17.PNG){ # fig:0017 width=70%} 


## Вывод:
В ходе работы я познакомилась с операционной системой Linux и получила практические навыки работы с редактором vi, установленным по умолчанию практически во всех дистрибутивах.
Ответы на контрольные вопросы:





