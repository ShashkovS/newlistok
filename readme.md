# Стиль для создания листков (занятий, кружков, собеседований и т.п.) по математике 

# Пример результата:
![alt text](https://raw.githubusercontent.com/ShashkovS/newlistok/master/list_demo_big.png)

См. также https://github.com/ShashkovS/newlistok/blob/master/list01__Geom_sum.pdf и https://github.com/ShashkovS/newlistok/blob/master/list03__Dir_sol.pdf.


## История

Пакет создан на основе стиля В.Крюкова (часть синтаксиса), используя некоторые идеи стиля Городенцева (автома-
тическая генерация кондуитов), а также сокращения стиля DMVN corp. Для русификации используются разработки
Львовского. Кроме того, документация части стиля, скопированной со стиля DMVN corp., также скопирована с до-
кументации к стилю DMVN. О DMVN можно узнать на http://www.dmvn.mexmat.ru


## Зависимости от других пакетов, установка

Пакет используют несколько стандартных пакетов: `amsfonts, amssymb, amsmath, epsf, graphicx, xcolor, microtype,
keyval, framed, inputenc, ifthen, bbding, marginnote, textcomp,ifthenx, pgf, pst-graphicx, babel-russian,
babel-english, geometry, cyrillic, cmcyr, lh, lhcyr, cm-super, collection-langcyrillic, fancybox, colortbl, standalone`. Все они входят в пол-
ный комплект TeX (например, в пакет MiKTeX, который можно скачать из архивов CTAN, а также в TeXLive). Часть
из них входит в минимальный пакет MikTeX’а для Windows и basic-пакет для TeXLive.

При использовании под Linux или Mac необходимо установить базовый `texlive-scheme-basic` и перечисленные
выше пакеты. Установить пакеты можно, например, командой

```bash
tlmgr install amsfonts amsmath epsf xcolor microtype framed bbding marginnote ifthenx pgf pst-graphicx
babel-russian babel-english geometry cyrillic cmcyr lh lhcyr cm-super collection-langcyrillic graphics
ifthenx fancybox colortbl standalone
```

Под Fedora пакетный менеджер tlmgr не ставится, нужно напрямую ставить через dnf:
```bash
sudo dnf -y install texlive-install
sudo dnf -y install texlive-amsfonts
sudo dnf -y install texlive-amsmath
sudo dnf -y install texlive-epsf
sudo dnf -y install texlive-xcolor
sudo dnf -y install texlive-microtype
sudo dnf -y install texlive-framed
sudo dnf -y install texlive-bbding
sudo dnf -y install texlive-marginnote
sudo dnf -y install texlive-ifthenx
sudo dnf -y install texlive-pgf
sudo dnf -y install texlive-pst-graphicx
sudo dnf -y install texlive-babel-russian
sudo dnf -y install texlive-babel-english
sudo dnf -y install texlive-geometry
sudo dnf -y install texlive-cyrillic
sudo dnf -y install texlive-cmcyr
sudo dnf -y install texlive-lh
sudo dnf -y install texlive-lhcyr
sudo dnf -y install texlive-cm-super
sudo dnf -y install texlive-collection-langcyrillic
sudo dnf -y install texlive-graphics
sudo dnf -y install texlive-ifthenx
sudo dnf -y install texlive-fancybox
sudo dnf -y install texlive-colortbl
sudo dnf -y install texlive-standalone
```



Под Windows пакеты можно установить при помощи менеджера mpm, который «живёт» по «адресу»
`.../texmf/miktex/bin/mpm.exe`.

Подключать пакет babel при использовании newlistok.sty не нужно. Компилировать файлы надо командой
PDFlatex или PDFTexify. При использовании важно создавать ваши файлы в кодировке WINDOWS-1251. Для то-
го, чтобы utf-8 предпочитающие редакторы сразу открывали ваши файлы в нужно кодировке, добавляйте первой
строчкой

```
% !TeX encoding = windows-1251
```


## Подключение и опции

Для использования всех возможностей достаточно подключить только пакет newlistok.sty, все остальные будут
подключены автоматически. В стандартной ситуации основной документ в преамбуле может содержать только одну
строку:

```tex
\usepackage{newlistok}
```



# Типичный листок

Начнём с самого простого примера. Исходный код типичного листочка будет выглядеть так:

```tex
\documentclass[12pt]{article}
\usepackage{newlistok}
\Заголовок{Предел последовательности\т 2}
\НомерЛистка{18}
\ДатаЛистка{12.2013}
\begin{document}
\СоздатьЗаголовок
\ввзадача[Теорема Вейерштрасса]
Докажите, что любая ограниченная монотонная последовательность сходится.
\кзадача
\задача
Докажите, что существует предел...
\кзадача
\опр
\label{Acc1}
Число~$a$ называется \emph{предельной точкой} последовательности~$(x_n)$,
если для всякого числа $\ep>0$ и~для любого $k\in\N$
существует такое натуральное $n>k$, что выполняется неравенство $|x_n-a|<\ep$.
\копр
\опр
\label{Acc2}
Точка~$a$ называется {\it предельной точкой} последовательности~$(x_n)$,
если любая окрестность точки~$a$ содержит бесконечно много точек последовательности~$(x_n)$.
\копр
\задача
Докажите эквивалентность определений~\ref{Acc1} и~\ref{Acc2}.
\кзадача
\задача
\пункт
Докажите, что если последовательность имеет предел, то этот предел является
предельной точкой и~других предельных точек нет.\\
\пункт
Верно ли, что если последовательность имеет единственную предельную точку,
то она (последовательность) является сходящейся?
\кзадача
\ввзадача[Критерий Коши]
\пункт Докажите, что сходящаяся последовательность является фундаментальной;
\пункт Докажите, что фундаментальная последовательность имеет предел.
\кзадача
\ЛичныйКондуит{0mm}{6mm}
\end{document}
```

Результат будет примерно такой:

![alt text](https://raw.githubusercontent.com/ShashkovS/newlistok/master/list_demo.png)



Если вам не нравится русский язык в командах, то нет проблем, такой вариант даст эквивалентный результат:

```tex
\documentclass[12pt]{article}
\usepackage{newlistok}
\ListTitle{Предел последовательности\т 2}
\ListNumber{18}
\ListDate{\mmyy}
\begin{document}
\CreateTitle
\begin{iiproblem}[Теорема Вейерштрасса]
Докажите, что любая ограниченная монотонная последовательность сходится.
\end{iiproblem}
\begin{problem}
Докажите, что существует предел...
\end{problem}
\begin{definition}
\label{Acc1}
Число~$a$ называется \emph{предельной точкой} последовательности~$(x_n)$,
если для всякого числа $\ep>0$ и~для любого $k\in\N$
существует такое натуральное $n>k$, что выполняется неравенство $|x_n-a|<\ep$.
\end{definition}
\begin{definition}
\label{Acc2}
Точка~$a$ называется {\it предельной точкой} последовательности~$(x_n)$,
если любая окрестность точки~$a$ содержит бесконечно много точек последовательности~$(x_n)$.
\end{definition}
\begin{problem}
Докажите эквивалентность определений~\ref{Acc1} и~\ref{Acc2}.
\end{problem}
\begin{problem}
\itm
Докажите, что если последовательность имеет предел, то этот предел является
предельной точкой и~других предельных точек нет.\\
\itm
Верно ли, что если последовательность имеет единственную предельную точку,
то она (последовательность) является сходящейся?
\end{problem}
\begin{iiproblem}[Критерий Коши]
\itm Докажите, что сходящаяся последовательность является фундаментальной;
\itm Докажите, что фундаментальная последовательность имеет предел.
\end{iiproblem}
\PersonalConduit{0mm}{6mm}
\end{document}
```


# Документация

Более подробную документацию см. в https://github.com/ShashkovS/newlistok/blob/master/newlistok.pdf.
