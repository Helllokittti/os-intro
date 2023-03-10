---
## Front matter
lang: ru-RU
title: Лабораторная работа №3
subtitle: Операционные системы
author:
  - Басманова Д.К.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 22 февраля 2023

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Басманова Дарья Кирилловна
  * студент
  * Российский университет дружбы народов

:::
::::::::::::::

# Вводная часть


## Объект и предмет исследования

- Легковесный язык разметки Markdown

## Цели и задачи

- Научиться оформлять отчёты с помощью легковесного языка разметки Markdown.


# Создание презентации


## Материалы и методы

- Процессор `pandoc` для входного формата Markdown
- Результирующие форматы
	- `pdf`
	- `html`
- Автоматизация процесса создания: `Makefile`

# Создание презентации

## Процессор `pandoc`

- Pandoc: преобразователь текстовых файлов
- Сайт: <https://pandoc.org/>
- Репозиторий: <https://github.com/jgm/pandoc>

## Формат `pdf`

- Использование LaTeX
- Пакет для презентации: [beamer](https://ctan.org/pkg/beamer)
- Тема оформления: `metropolis`

## Код для формата `pdf`

```yaml
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
```

## Формат `html`

- Используется фреймворк [reveal.js](https://revealjs.com/)
- Используется [тема](https://revealjs.com/themes/) `beige`

## Код для формата `html`

- Тема задаётся в файле `Makefile`

```make
REVEALJS_THEME = beige 
```

## Задание

Сделайть отчёт по предыдущей лабораторной работе в формате Markdown.
В качестве отчёта просьба предоставить отчёты в 3 форматах: pdf, docx и md (в архиве,поскольку он должен содержать скриншоты, Makefile и т.д.)

## Теоретическое введение

**Базовые сведения о Markdown**

Чтобы создать заголовок, используйте знак ( # ), например:

1 # This is heading 1

2 ## This is heading 2

3 ### This is heading 3

4 #### This is heading 4

Чтобы задать для текста полужирное начертание, заключите его в двойные звездочки:

1 This text is **bold**.

Чтобы задать для текста курсивное начертание, заключите его в одинарные звездочки:

1 This text is *italic*.

Чтобы задать для текста полужирное и курсивное начертание, заключите его в тройные звездочки:
1 This is text is both ***bold and italic***.

##Блоки цитирования создаются с помощью символа >:

1 > The drought had lasted now for ten million years, and the reign of
the terrible lizards had long since ended. Here on the Equator, in
the continent which would one day be known as Africa, the battle
for existence had reached a new climax of ferocity, and the victor
was not yet in sight. In this barren and desiccated land, only the
small or the swift or the fierce could flourish, or even hope to
survive.

Неупорядоченный (маркированный) список можно отформатировать с помощью звез-
дочек или тире:
1 - List item 1
2 - List item 2
3 - List item 3
Чтобы вложить один список в другой, добавьте отступ для элементов дочернего списка:

34 Лабораторная работа No 3. Markdown

1 - List item 1
2 - List item A
3 - List item B
4 - List item 2

##Упорядоченный список можно отформатировать с помощью соответствующих цифр:

1 1. First instruction
2 1. Second instruction
3 1. Third instruction

Чтобы вложить один список в другой, добавьте отступ для элементов дочернего списка:

1 1. First instruction
2 1. Sub-instruction
3 1. Sub-instruction
4 1. Second instruction

##Синтаксис Markdown для встроенной ссылки состоит из части , представляющей текст гиперссылки, и части (file-name.md) – URL-адреса или имени файла, на который дается ссылка:

Markdown поддерживает как встраивание фрагментов кода в предложение, так и их
размещение между предложениями в виде отдельных огражденных блоков. Огражденные
блоки кода — это простой способ выделить синтаксис для фрагментов кода. Общий
формат огражденных блоков кода:
1 ``` language
2 your code goes in here
3 ```
Верхние и нижние индексы:
𝐻2
записывается как
1 H~2~O
210
записывается как
1 2^10^
##Внутритекстовые формулы делаются аналогично формулам LaTeX. Например, формула
sin2(𝑥) + cos2(𝑥) = 1 запишется как
1 $\sin^2 (x) + \cos^2 (x) = 1$
Выключные формулы:
sin2(𝑥) + cos2(𝑥) = 1
{#eq:eq:sin2+cos2} со ссылкой в тексте  записывается как
1 $$
2 \sin^2 (x) + \cos^2 (x) = 1
3 $$ {#eq:eq:sin2+cos2}
4
5 Смотри формулу 
3.2.2. Обработка файлов в формате Markdown
##Для обработки файлов в формате Markdown будем использовать Pandoc
https://pandoc.org/. Конкретно, нам понадобится программа pandoc ,
pandoc-citeproc https://github.com/jgm/pandoc/releases, pandoc-crossref
https://github.com/lierdakil/pandoc-crossref/releases.
Преобразовать файл README.md можно следующим образом:
1 pandoc README.md -o README.pdf
или так
1 pandoc README.md -o README.docx
Можно использовать следующий Makefile
1 FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
2 FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
3
4 LATEX_FORMAT =
5
6 FILTER = --filter pandoc-crossref
7
8 %.docx: %.md
9 -pandoc "$<" $(FILTER) -o "$@"
10
11 %.pdf: %.md
12 -pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
13
14 all: $(FILES)
15 @echo $(FILES)
16
17 clean:
18 -rm $(FILES) *~

## Выполнение лабораторной работы


Для начала работы мы подготваливаем скриншоты для отчета. Далее начинаем оформлять титульный лист. (см.Начало отчета).


![Начало отчета](image/Начало отчета.png){#fig:001 width=70%}

Дальше пишем цели и задачи нашей работы.


Далее начинаем выполнение описания нашей лабораторной работы.

![Начало отчета](image/Начало отчета.png){#fig:002 width=70%}

## Выводы

Я научилась оформлять отчёты с помощью легковесного языка разметки Markdown.


::: {#refs}

:::

