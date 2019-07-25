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
babel-english, geometry, cyrillic, cmcyr, lh, lhcyr, cm-super, collection-langcyrillic, fancybox, colortbl, standalone`. Все они входят в полный комплект TeX (например, в пакет MiKTeX, который можно скачать из архивов CTAN, а также в TeXLive). Часть
из них входит в минимальный пакет MikTeX’а для Windows и basic-пакет для TeXLive.

При использовании под Linux или Mac необходимо установить базовый `texlive-scheme-basic` и перечисленные
выше пакеты. Чтобы установить `texlive` на MacOs нужно скачать файл http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz, распаковать и выполнить `sudo ./install-tl`. Выбрать по S схему basic, по O->L добавить symlink'и, и запустить установку I.
Установить пакеты после этого можно командой

```bash
sudo tlmgr install amsfonts amsmath epsf xcolor microtype framed bbding marginnote ifthenx pgf pst-graphicx babel-russian babel-english geometry cyrillic cmcyr lh lhcyr cm-super collection-langcyrillic graphics ifthenx fancybox colortbl standalone
```

Под Fedora пакетный менеджер tlmgr не ставится, нужно напрямую ставить через dnf:
```bash
sudo dnf -y install texlive-install texlive-amsfonts texlive-amsmath texlive-epsf texlive-xcolor texlive-microtype texlive-framed texlive-bbding texlive-marginnote texlive-ifthenx texlive-pgf texlive-pst-graphicx texlive-babel-russian texlive-babel-english texlive-geometry texlive-cyrillic texlive-cmcyr texlive-lh texlive-lhcyr texlive-cm-super texlive-collection-langcyrillic texlive-graphics texlive-ifthenx texlive-fancybox texlive-colortbl texlive-standalone 
```

Впрочем и под Linux'ом, и особенно под Mac удобнее установить MikTeX со страницы https://miktex.org/download.

Под Windows можно использовать также TeXLive, либо (лучше) MikTeX. В этом случае пакеты можно установить при помощи менеджера mpm, который «живёт» по «адресу»
`.../texmf/miktex/bin/mpm.exe`.

```bash
mpm --require="amsfonts amsmath epsf graphics xcolor microtype xkeyval framed ifthenx bbding marginnote pgf pst-graphicx babel-russian babel-english geometry cyrillic cmcyr lh lhcyr cm-super fancybox colortbl standalone"
```

Подключать пакет babel при использовании newlistok.sty не нужно. Компилировать файлы надо командой
PDFlatex или PDFTexify. При использовании важно создавать ваши файлы в кодировке WINDOWS-1251. Для то-
го, чтобы utf-8 предпочитающие редакторы сразу открывали ваши файлы в нужно кодировке, добавляйте первой
строчкой

```
% !TeX encoding = windows-1251
```
## В чём писать
Для подготовки листков крайне рекомендуется использовать среду https://texstudio.org.

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
