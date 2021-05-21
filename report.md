---
# Front matter
lang: ru-RU
title: "отчёта по лабораторной работе 10"
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
Познакомиться с операционной системой Linux. Получить практические навыки работы с редактором Emacs.

## Выполнение работы.
1   1.	Открыли emacs.  (рис. -@fig:001)

![1](image/1.PNG) { # fig:001 width=70%} 
 
2.	Создали файл lab07.sh с помощью комбинации Ctrl-x Ctrl-f (C-x C-f). 
3.	Набрали текст: 
 #!/bin/bash
HELL=Hello 
function hello { 
LOCAL HELLO=World 
echo $HELLO
} 
echo $HELLO 
hello
(рис. -@fig:002)

![2](image/2.PNG) { # fig:002 width=70%} 

4. Сохранить файл с помощью комбинации Ctrl-x Ctrl-s (C-x C-s).
5. Проделать с текстом стандартные процедуры редактирования, каждое действие
должно осуществляться комбинацией клавиш.
5.1. Вырезать одной командой целую строку (С-k).
(C-x C-s). (рис. -@fig:003)

 ![3](image/3.PNG) { # fig:003 width=70%} 

5.2. Вставить эту строку в конец файла (C-y).:(рис. -@fig:004)

 ![4](image/4.PNG) { # fig:004 width=70%} 
 #!/bin/bash
HELL=Hello
function hello {
LOCAL HELLO=World
echo $HELLO
}
echo $HELLO
hello


5.3. Выделить область текста (C-space) : (рис. -@fig:005)

![5](image/5.PNG) { # fig:005 width=70%} 

5.4. Скопировать область в буфер обмена (M-w).
5.5. Вставить область в конец файла. : (рис. -@fig:006)

 ![6](image/6.PNG) { # fig:006 width=70%} 

5.6. Вновь выделить эту область и на этот раз вырезать её (C-w).(рис. -@fig:007)

 ![7](image/7.PNG) { # fig:007 width=70%} 

 5.7. Отмените последнее действие (C-/). (рис. -@fig:008)

 ![8](image/8.PNG)  { # fig:008 width=70%}  </br></br>
Задание 2. Редактирование существующего файла

6. Научитесь использовать команды по перемещению курсора.
6.1. Переместите курсор в начало строки (C-a).
(рис. -@fig:009)

 ![9](image/9.PNG)  { # fig:009 width=70%} 

6.2. Переместите курсор в конец строки (C-e). (рис. -@fig:0010)

 ![10] (image/10.PNG) { # fig;0010 width=70%} 

6.3. Переместите курсор в начало буфера (M-<). .(рис. -@fig:0011)
 ![11](image/11.PNG) { # fig:0011 width=70%} 
	
6.4. Переместите курсор в конец буфера (M->). (рис. -@fig:0012)

 ![12](image/12.PNG) { # fig:0012 width=70%} 
 
7. Управление буферами.
7.1. Вывести список активных буферов на экран (C-x C-b). (рис. -@fig:0013)

 ![13](image/13.PNG) { # fig:0013 width=70%} 
 
7.2. Переместитесь во вновь открытое окно (C-x) o со списком открытых буферов и переключитесь на другой буфер. (рис. -@fig:0015)

 ![15](image/15.PNG) { # fig:0015 width=70%} 

7.3. Закройте это окно (C-x 0). (рис. -@fig:0016)

  ![16](image/16.PNG) { # fig:0016 width=70%} 

7.4. Теперь вновь переключайтесь между буферами, но уже без вывода их списка
на экран (C-x b). (рис. -@fig:0017)

  ![17](image/17.PNG) { # fig:0017 width=70%} 
  
8. Управление окнами.
1.2.	8.1. Поделили фрейм на 4 части: разделили фрейм на два окна по вертикали (C-x 3), а затем каждое из этих окон на две части по горизонтали (C-x 2).
(рис. -@fig:0018) 

  ![18](image/18.PNG){ # fig:0018 width=70%} 

8. 8.2 В каждом из четырёх созданных окон откройте новый буфер (файл) и введите несколько строк текста (рис. -@fig:0018) 

  ![18](image/18.PNG){ # fig:0018 width=70%} 

9. Режим поиска
9.1. Переключитесь в режим поиска (C-s) и найдите несколько слов, присутствующих в тексте. (рис. -@fig:0019) 

  ![19](image/19.PNG){ # fig:0019 width=70%} 

9.2. Переключайтесь между результатами поиска, нажимая C-s.
(рис. -@fig:0020) 

  ![20](image/20.PNG){ # fig:0020 width=70%} 

 9.3. Выйдите из режима поиска, нажав C-g. (рис. -@fig:0021) 

  ![21](image/21.PNG){ # fig:0021 width=70%} 

  9.4. Перейдите в режим поиска и замены (M-%), введите текст, который следует
найти и заменить, нажмите Enter , затем введите текст для замены. После того как будут подсвечены результаты поиска, нажмите ! для подтверждения
замены. (рис. -@fig:0023) 

  ![23](image/23.PNG) { # fig:0023 width=70%} 

9.4. Перейдите в режим поиска и замены (M-%), введите текст, который следует
найти и заменить, нажмите Enter , затем введите текст для замены. После того как будут подсвечены результаты поиска, нажмите ! для подтверждения
замены. (рис. -@fig:0024) 

![24](image/24.PNG) { # fig:0024 width=70%} 


## Вывод:
В ходе работы мы подробнее познакомились с операционной системой Linux, а также получили практические навыки работы с редактором Emacs.



## Ответы на контрольные вопросы:
1. Emacs представляет собой мощный экранный редактор текста, написанный на языке высокого уровня Elisp. 
2. Для работы с Emacs можно использовать как элементы меню, так и различные сочетания клавиш. Многие рутинные операции в Emacs удобнее производить с помощью клавиатуры, а не графического меню. 
3. Буфер—объект, представляющий какой-либо текст. Окно — прямоугольная область фрейма, отображающая один из буферов. 
4. Да, можно. 
5. Буфер файла. 
6. Ctrl+c+\ и Ctrl+\ 
7. Ctrl+x+4(по горизонтали) или Ctrl+x+3(по вертикали) 
8. .emacs 
9. Перемещает курсор на 1 символ влево. Нельзя. 
10. Мне показался наиболее удобным редактор vi, так как его интерфейс намного проще



