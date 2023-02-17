---
## Front matter
title: "Лабораторная работа №1"
subtitle: "Архитектура вычислительных систем"
author: "Басманова Дарья Кириллова"

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

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов

# Задание

Лабораторная работа подразумевает установку на виртуальную машину VirtualBox.

# Выполнение лабораторной работы


1) Запустиv терминал. Перейдtv в каталог /var/tmp:
Создаlbv каталог с именем пользователя (совпадающий с логином в дисплейном классе). 

![5](image/5.jpg){#fig:001 width=70%}

2) Настройка хост-клавиши
 Хост-клавишей по умолчанию является правый Ctrl. По умолчанию в дисплейных классах на клавише правый Ctrl находится переключатель языка ввода.
 
        В меню выберите Файл, Настройки.
        Выберите Ввод, вкладка Виртуальная машина.
        Выберите Сочетание клавиш в строке Хост-комбинация.
        Нажмите новое сочетание клавиш.
        Нажмите ОК, чтобы сохранить изменения.

   Сделаем нужную клавижу (Меню)

   
![2](image/2.jpg){#fig:002 width=70%}
![3](image/3.jpg){#fig:003 width=70%}

3) Создание виртуальной машины
Запустим менеджер виртуальных машин, введя в командной строке:

    Создадим новую виртуальную машину.
    Укажем имя виртуальной машины (логин в дисплейном классе), тип операционной системы — Linux, Fedora.
    Укажем размер основной памяти виртуальной машины — от 2048 МБ.
    Зададим конфигурацию жёсткого диска — загрузочный, VDI (VirtualBox Disk Image), динамический виртуальный диск.
    Зададим размер диска — 80 ГБ (или больше), его расположение
    Выберем в VirtualBox Вашей виртуальной машины. Добавьте новый привод оптических дисков и выберите образ.
  
![4](image/4.jpg){#fig:004 width=70%}

4) После установки 
    Выбираем язык интерфейса и перейдем к настройкам установки операционной системы.
    Место установки ОС оставляем без изменения.
    Установим имя и пароль для пользователя root.
    Установим имя и пароль для Вашего пользователя.
    Зададим сетевое имя Вашего компьютера.
    После завершения установки операционной системы корректно перезапустим виртуальную машину.
    В VirtualBox оптический диск должен отключиться автоматически.

5) Войдем в в ОС под заданной при установке учётной записью.
    Нажмем комбинацию Win+Enter для запуска терминала.

    Переключитесь на роль супер-пользователя:

    sudo -i
![9](image/9.jpg){#fig:005 width=70%}
Обновления
Обновить все пакеты
Повышение комфорта работы   
Автоматическое обновление
 При необходимости можно использовать автоматическое обновление
    Установка программного обеспечения:
    dnf install dnf-automatic
    Задаёте необходимую конфигурацию в файле /etc/dnf/automatic.conf.
    Запустите таймер:
    systemctl enable --now dnf-automatic.timer
Отключение SELinux
    В данном курсе мы не будем рассматривать работу с системой безопасности SELinux.
    Поэтому отключим его.
    В файле /etc/selinux/config замените значение
    SELINUX=enforcing

    на значение

    SELINUX=permissive
![17](image/17.png){#fig:006 width=70%}
    Перегрузите виртуальную машину:

    reboot
готовая машина
![19](image/19.png){#fig:007 width=70%}




# Выводы

Я приобрела практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.


