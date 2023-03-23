---
## Front matter
title: "Индивидуальный проект 2 этап"
subtitle: "Операционные системы"
author: "Басманова Д.К."

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

Добавить к сайту данные о себе.

# Задание

Список добавляемых данных.
1. Разместить фотографию владельца сайта.
2. Разместить краткое описание владельца сайта (Biography).
3. Добавить информацию об интересах (Interests).
4. Добавить информацию от образовании (Education).
5. Сделать пост по прошедшей неделе.
6. Добавить пост на тему по выбору:
7. Управление версиями. Git.
8. Непрерывная интеграция и непрерывное развертывание (CI/CD).


# Выполнение лабораторной работы


Описываются проведённые действия, в качестве иллюстрации даётся ссылка на иллюстрацию (рис. @fig:001).

После выполнения этапа №1, мы получили сайт и файлы, которые можем редактировать. Для добавления и изменения сайта мы заходим в файлы с помощью gedit. 
Первым делом нам нудно изменить фотографию на сайте. Для этого в папке autor добавляем фото и меняем его название. 
Так же в этой папке меняем описание владельца сайта и добавляем информацию об интересах и образовании. 
В итоге мы получаем следующий вид сайта:

 ![Мой сайт](image/1.png){#fig:001 width=70%}
 
  ![Изменения в файле gedit](image/2.png){#fig:002 width=70%}

Дальше нам нужно сделать пост по прошедшей неделе. 
Для этого заходим в папку с другим постом в папке посты. Изменяем и добавляем фотографию и информацию в файл. 

В итоге у нас получился пост.

![Мой пост](image/3.png){#fig:003 width=70%}

Продолжаем редактировать наш сайт 
Нам нужно добавить пост на тему по выбору:
Управление версиями. Git.
Непрерывная интеграция и непрерывное развертывание (CI/CD).
Я выбрала 1 тему.

В итоге у меня получился пост:

![Мой пост 2](image/4.png){#fig:004 width=70%}

# Выводы

Я научилась редактировать сайт. Добавлять посты и изменять информацию в них.

