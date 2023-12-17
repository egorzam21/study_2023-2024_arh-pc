---
## Front matter
title: "Лабораторная работа №6"
subtitle: "Арифметические операции в NASM"
author: "Замула Егор Сергеевич"

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

Освоение арифметических инструкций языка ассемблера NASM.

# Теоретическое введение

Большинство инструкций на языке ассемблера требуют обработки операндов. Адрес опе-
ранда предоставляет место, где хранятся данные, подлежащие обработке. Это могут быть
данные хранящиеся в регистре или в ячейке памяти. Далее рассмотрены все существующие
способы задания адреса хранения операндов – способы адресации.
Существует три основных способа адресации:
• Регистровая адресация – операнды хранятся в регистрах и в команде используются
имена этих регистров, например: mov ax,bx.
• Непосредственная адресация – значение операнда задается непосредственно в ко-
манде, Например: mov ax,2.
• Адресация памяти – операнд задает адрес в памяти. В команде указывается символи-
ческое обозначение ячейки памяти, над содержимым которой требуется выполнить
операцию.

# Выполнение лабораторной работы

1. Создал каталог для программам лабораторной работы № 6, перешёл в него и создал файл lab6-1.asm

![Создание каталога](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-12-53.png){#fig:001 width=70%}

2. Ввел в файл lab6-1.asm текст программы из листинга 6.1.

![Ввод текста из листинга6.1](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-15-08.png){#fig:002 width=70%}

3. Создал исполняемый файл и запустил его.

![Запуск исполняемого файла](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-23-25.png){#fig:003 width=70%}

4. Далее изменил текст программы и вместо символов, записал в регистры числа. 

![Изменение текста программы](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-25-23.png){#fig:004 width=70%}

5. Создал исполняемый файл и запустил его. Этот символ не будет отражаться

![Запуск измененного исполняемого файла](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-27-57.png){#fig:005 width=70%}

6. Создал файл lab6-2.asm в каталоге ~/work/arch-pc/lab06 и ввел в него текст программы из листинга 6.2.

![Создание файла lab6-2.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-32-07.png){#fig:006 width=70%}

7. Создаю исполняемый файл и запускаю его. Получаем число 106. 

![Запуск исполняемого файла](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-35-55.png){#fig:007 width=70%}

8. Аналогично предыдущему примеру изменим символы на числа. 

![Изменяем файл lab6-2.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-37-30.png){#fig:008 width=70%}

9. Создаю исполняемый файл и запускаю его. Получаем ответ 10. 

![Запуск изменённого файла](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-39-08.png){#fig:009 width=70%}

10. Создал файл lab6-3.asm в каталоге ~/work/arch-pc/lab06, изучил текст программы из листинга 6.3 и ввел в lab6-3.asm.

![Создание файл lab6-3.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-47-55.png){#fig:010 width=70%}

11. Создал исполняемый файл и запустил его. Результат должен получится 4, а остаток 1. 

![Запуск файла lab6-3.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-50-29.png){#fig:011 width=70%}

12. Изменил текст программы для вычисления выражения. 

![Изменяю текст файла lab6-3.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-53-05.png){#fig:012 width=70%}

13. Создаю исполняемый файл и проверяю его работу. Результат вычисления должен быть 5, и остаток 1.

![Запуск изменеённого файла](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-55-34.png){#fig:013 width=70%}

14. Создаю файл variant.asm в каталоге ~/work/arch-pc/lab06

![Создаю файл variant.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2011-58-42.png){#fig:014 width=70%}

15. Внимательно изучил текст программы из листинга 6.4 и ввел в файл variant.asm.

![Изменяю файл variant.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2012-00-49.png){#fig:015 width=70%}

16. Создал исполняемый файл и запустил его. Проверил результат работы программы вычислив номер варианта аналитически.Мой вариант 17. 

![Создаю файл variant.asm](https://raw.githubusercontent.com/egorzam21/study_2023-2024_arh-pc/3119113e9c28764ea0fc89c8904d14609950e433/labs/lab06/report/image/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-12-17%2012-04-02.png){#fig:016 width=70%}

17. Ответы на вопросы: 

1) mov eax, rem call sprint 

2) mov eax, х - используется для записи входной переменной в регистр ecx; mov edx, 80 - запись размера переменной в регистр edx; call sread - вызов процедуры чтения данных

3) это функция преобразующая ascii-код символа в целое число и записывающий результат в регистр eax.

4) xor edx, edx mov, 20 div ebx inc edx

5) B ebx

6) Инструкция inc используется для увеличения операнда на еденицу

7) mov eax, rem call sprint mov eax, edx call iprintLF

# Выводы

Я освоил арифметические инструкции языка ассемблера NASM.

# Список литературы{.unnumbered}

::: {#refs}
:::
