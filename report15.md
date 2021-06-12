---
# Front matter
lang: ru-RU
title: "отчёта по лабораторной работе 15"
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
Приобретение практических навыков работы с именованными каналами.


## Выполнение работы.
Ход работы:
1.	Мы изучили и написали приведенные в тексте задания к лабораторной работе программы common.h, server.c и client.c

  (рис. -@fig:001)

![1](image/1.PNG) { # fig:001 width=70%}
(рис. -@fig:002)

![2](image/2.PNG) { # fig:002 width=70%} 

 (рис. -@fig:003)

 ![3](image/3.PNG) { # fig:003 width=70%} 

 ![4](image/4.PNG) { # fig:004 width=70%} 


 Как видно сервер откликается через 5 секунд от каждого нового запуска клиента, а через 30 секунд программа завершается с выводом общего количества времени и интервал от последнего отклика клиента до завершения сервера

 Если сервер завершит работу не закрыв канал, то при следующем запуске будет выведено следующее (errno)


## Вывод:
Написали FIFO канал на C (server/client)

## Ответы на контрольные вопросы:
1.	В чем ключевое отличие именованных каналов от неименованных? Именованные каналы отличаются от неименованных наличием идентификатора канала, который представлен как специальный файл (соответственно имя именованного канала — это имя файла).

2.	Возможно ли создание неименованного канала из командной строки? Неименованные каналы создаются вызовом pipe() и предоставляют возможность только однонаправленной (односторонней) передачи данных:

#include <unistd.h> int fd[2];
pipe(fd);

/* возвращает 0 в случае успешного завершения, -1 - в случае ошибки;*/


Функция возвращает два файловых дескриптора: fd[0] и fd[l], причемпервый открыт для чтения, а второй – для записи.

Возможно создание неименованного канала из командной строки только с созданием временного именнованного канала.

3. Возможно ли создание именованного канала из командной строки?

Да, с помощью mkfifo или, использованной с давних времен, mknod


4. Опишите функцию языка С, создающую неименованный канал. #include <unistd.h>

int fd[2]; pipe(fd);
 
/* возвращает 0 в случае успешного завершения, -1 - в случае ошибки;*/


Функция возвращает два файловых дескриптора: fd[0] и fd[l], причемпервый открыт для чтения, а второй – для записи.

5. Опишите функцию языка С, создающую именованный канал. #include <sys/types.h>

#include <sys/stat.h>


int mkfifo(const char *pathname, mode_t mode);


6. Что будет в случае прочтения из fifo меньшего числа байтов, чем находится в канале? Большего числа байтов?

При чтении меньшего числа байтов, чем находится в канале или FIFO,

возвращается требуемое число байтов, остаток сохраняется для последующих чтений.


При чтении большего числа байтов, чем находится в канале или FIFO, возвращается доступное число байтов. Процесс, читающий из канала, должен соответствующим образом обработать ситуацию, когда прочитано меньше, чем заказано.

7. Аналогично, что будет в случае записи в fifo меньшего числа байтов, чем позво-ляет буфер? Большего числа байтов?

Запись числа байтов, меньшего емкости канала или FIFO, гарантированно атомарно. Это означает, что в случае, когда несколько процессов одновременно записывают в канал, порции данных от этих процессов не перемешиваются.

При записи большего числа байтов, чем это позволяет канал или FIFO, вызов write(2) блокируется до освобождения требуемого места. При этом атомарность операции не гарантируется. Если процесс пытается записать данные в канал, не открытый ни одним процессом на чтение, процессу генерируется сигнал SIGPIPE, а вызов write(2) возвращает 0 с установкой ошибки (errno=ЕР1РЕ) (если процесс не установил обработки сигнала SIGPIPE, производится обработка по умолчанию -- процесс завершается).
 

8. Могут ли два и более процессов читать или записывать в канал?

Да, если введено достаточное количество байтов для buff, при этом порции процессов не перемешиваются, иначе, при большем вводе байтов, чем указано, возможна ошибка.

9.	Опишите функцию write (тип возвращаемого значения, аргументы и логику ра-боты). Что означает 1 (единица) в вызове этой функции в программе server.c (строка 42)?

Функция записывает length байтов из буфера buffer в файл, определенный дескриптором файла fd. Эта операция чисто 'двоичная' и без буферизации. При единице возвращает действительное число байтов.

Функция write возвращает число действительно записанных в файл байтов или -1 при ошибке, устанавливая при этом errno.



10.	Опишите функцию strerror

Используется, чтоб получить pointer к ошибке в строке буффера и возврата errnum, выводя сообщения с указанием errno. Чаще используется strerror_s (secured — защищенный), нежели strerror из-за безопасности и утечки данных.
