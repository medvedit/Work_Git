<a id="anchor"></a>

# Инструкция для работы с *Git* и удаленным репозиториями.

***
## ***Что такое Git...?***
+ ***Git*** - это одна из реализаций распространённых систем контроля версий, имеющая, как и локальные, так и удаленные репозитории. Является самой популярной реализацией систем контроля версий в мире.
***

# ***Работа локально:***
## *Подготовка репозитория:*

+ Что бы посмотреть версию программы Git, нужно ввести команду:
>***git*** пробел --version
>>git --version


+ Для создания репозитория необходимо выполнить команду ***\*git init\****
>Напишите команду: ***git*** пробел ***init***
>>***git init***

В папке с репозиторием у Вас появится репозиторий, скрытая папка ***.git***

## *Просмотр состояния репозитория*:

+ Для того, что бы посмотреть состояние репозитория используется команда ***\*git status\****. Что бы увидеть были ли изменения в файлах, или их не было
>Напишите команду: ***git*** пробел ***status***
>>***git status***

## *Фиксация состояния*:

+ Команда ***\*git add\**** перемещает из рабочей папки в область индексирования предназначенное для следующей фиксации содержимое. Для создания фиксации изменений в рабочем файле используется команда ***\*git add\****. Что бы зафиксировать изменения
>Напишите команду: ***git*** пробел ***add*** пробел ***<Имя файла>***
>>***git add <имя файла>***

## *Создание коммитов*:

+ Для того, чтобы создать коммит(сохранение) необходимо выполнить команду ***\*git commit\****. Выполняется она так:
>Напишите команду: ***git commit*** пробел ***-m*** пробел ***"сообщение к коммиту"*** (обязательно в кавычках)
>>***git commit -m "текст коммита"***


Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** (cmd+S для Мас) и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

## *Журнал изменений, коммитов*:

+ Для того, чтобы посмотреть все сделанные сохранения в репозитории, используется команда ***\*git log\****. Для этого достаточно выполнить команду в папке с репозиторием:

>***git*** пробел ***log***
>> ***git log***

+ Для того, что бы посмотреть всю историю коммитов в сокращенном виде на ветке, на котрой вы сейчас находитесь, используется команда ***\*git log --online*\***

>***git*** пробел ***log*** пробел ***--online***
>>***git log --online***

+ Что бы посмотреть историю в виде дерева, необходимо ввести команду:
>***git*** пробел ***log*** пробел ***--graph***
>>git log --graph
## *Перемещение между сохранениями, коммитами*:

+ Для того, чтобы посмотреть все сделанные изменения в репозитории, используется команда ***\*git checkout\****. Используется она в папке с репозиторием следующим образом:
>***git checkout*** пробел ***<номер коммита>*** (достаточно первые четыре знака).
>>***git checkout <первые четыре знака>***


Для ввода номера коммита достаточно первых четырёх знаков.

## *Возврат в последнее сохранённое состояние, не переходя в другу ветку, для продолжения работы* :

+ Для этого используется команда :
>***git*** пробел ***checkout*** пробел ***<имя ветки>***
>>***git checkout master***

***

# ***Создание веток:***

## *Создание ветки* :

+ Для того, чтобы создать ветку, используется команда ***\*git branch\****. Делается это следующим образом в папке с репозиторием:
>***git*** пробел ***branch*** пробел ***<название новой ветки>***
>>***git branch main***

## *Слияние веток* :

+ Для того чтобы добавить ветку в текущую ветку используется команда :

>***git*** пробел  ***merge*** пробел ***<имя ветки\>***
>>***git merge <имя ветки>***

## *Удаление веток* :

+ Для удаления локальной ветки ввести команду:

>***git*** пробел ***branch*** пробел  ***-d*** пробел ***<имя ветки>***
>>***git branch -d <имя ветки>***

# ***Работа с удаленным репозиторием:***

+ Для того, что бы начать работу с удаленным репозиторием, со своего аккаунта, необходимо его скачать себе локально (предположим, что этого репозитория у вас нет локально в данны момент, так случилось, что вы продолжаете работу с этим репозиторием на другом компьютере). Для этого переходим в этот репозиторий в GitHub, в правом верхнем углу открытого репозитория будет зеленая клавиша *Code*, нажав на нее нужно *скопировать ссылку* на репозиторий в формате *HTTPS* и после этого командой внутри *VScode\Git*
>***git*** пробел ***clone*** пробел ***<ссылка на репозиторий>***
>>***git clone >ссылка<***

+ Репозиторий можно скачать в не инициализированную папку, в этом случае для работы в скаченном репозитории необходимо будет переместиться между папками (перейти в папку со скаченным репозиторием). Это делается следующей командой:
>***cd*** пробел ***<имя папки>***

+ Для того, что бы залить новый, созданный локально репозиторий в удаленный сервис, вам нужно иметь свой аккаунт на этом сервисе. Рассорим на примере сервиса GitHub. В вернем правам углу страницы GitHub нажать +, новый репозиторий, дать ему имя, создать репозиторий(Create repository). Далее будет предложено три варианта действий на выбор:

1) Вы можете создать новый репозиторий через терминал и начать с ним работать
2) Уже существующий репозиторий привязать к этому удаленному репозиторию
3) либо импортировать код из другого репозитория

Наш вариант второй. Для этого копируем поочередно три команды из предложенных и поочередно вводим их в терминале VScode\Git
> ***git remote add origin <ссылка на репозиторий>***

> ***git branch -M main***

> ***git push -u origin main***

***remote*** - удаленный, то есть по сути мы связываем наш локальный репозиторий с удаленным ссылкой в конце этой команды. Второй командой мы говорим какая ветка у нас будет основной, а последней командой мы отправляем наш локальный репозиторий в удаленный.

+ Далее, после того как мы привязали наш локальный репозиторий с удаленным, при следующей отправке изменений в рабочем файле локального репозитория на удаленный достаточно будет короткой команды:

>***git push***

+ Предположим, что на GitHub версия репозитория у вас более актуальна, чем в вашей локальной. Возможно вы внесли изменения с другого компьютера, то для заливки актуальной версии из удаленного репозитория в вашу локальную используется команда:
>***git pull***

***pull*** является составной командой. Она не только перенесет все изменения из удаленной в локальную, но и попытается их смежить/слияние.

+ Для отвязки локального репозитория от удаленного вначале вводим команду ***git remote -v show*** после чего нам покажет имя и ссылку на связанный удаленный репозиторий. Затем для отвязки/удаления имяни и ссылки вводим команду ***git remote remove <имя>*** Сейчас можно привязать локальный к другому, новому удаленному репозиторию.
>git remote -v show
>>git remote remove <имя>
# Compare & Pull Request

+ Предположим есть не вами созданный репозиторий, но он вам необходим для работы.

1) Делаем копию репозитория в свой аккаунт с помощью кнопки ***\*Fork\**** После нажатия ***\*Fork\**** мы получаем полную копию этого репозитория на свой аккаунт, и с этим репозиторием мы уже можем работать.
2) С помощью команды ***git clone*** и ссылки на нужный нам репозиторий мы скачиваем его локально, в наш терминал.
3) После загрузки репозитория в локальную копию, ***НЕ ЗАБЫВАЕМ ПЕРЕЙТИ В ПАПУ С РЕПОЗИТОРИЕМ ДЛЯ РАБОТЫ В НЕМ*** с помощью команды ***cd <имя файла>***
4) Чтобы внести изменения в скаченный нами проект, предложить изменения в этом проекте, необходимо работать в отдельной ветке. ***Создаем ветку и работаем только в ней!!!***
5) Работаем с проектом не забывая по необходимости делать ***git add*** и ***git commit***.
6) После окончания работы в репозитории мы можем предложить на рассмотрение внесенные нами изменения в проект изначальному владельцу этого репозитория. Для этого изначально отправляем этот репозиторий в наш локальный командой ***git push***. После ввода этой команды Git может подсказать точную команду для отправки, Git часто подсказывает)))
7) Переходим на страницу GitHub, обновляем страницу и можем увидеть что в проекте появилась созданная нами ветка с нашей работай и кнопка ***Compare & Pull Request (Сравни & Отправь запрос)*** После перехода по этой кнопке можно добавить описание и все отправить владельцу проекта.


# Добавление активной ссылки на сайт в виде текста:
>Команда для добавления ссылки в виде текста выглядит следующим образом: \[тот текст который будет виден]\(сама ссылка на сайт)

[Работа с Markdown](https://lifehacker.ru/chto-takoe-markdown/)

# Добавление текста в виде *цитаты*:

>Для добавления текста в виде цитаты выполняется следующая команда: \>Текст
>>Подцитата-команда: >>Текст
>>>Можно углубиться еще в цитату))), для этого нужно ввести: \>>>Текст

# Оформление списков:

## Нумерованные списки:

>Для добавления нумерованных списков вводится следующая команда: 1.пробел, а далее текст

1. Первое
2. Второе
3. Третье

## Не нумерованные списки:

>Для добавления не нумерованных списков необходимо ввести: *пробел, и далее текст или +пробели текст, а можно -пробел  и текст.

* Первое
+ Второе
- Третье

***
>А выше этой цитаты, которую Вы сейчас читаете линия, которую можно которую можно начертить поставив три звёздочки подряд:

> \***
# Добавление кода в текст:

>Для добавления кода в выделенной области, что бы это выглядело как листинг программного кода используются троекратные опострофы  \```. Апострофы выше коду и в следующей строке, под кодом. Если после тройного апострофа выше когда добавить название языка, то код будет подсвечен, например - \```C#

>>\```C#

>>[код или текст]

>>\```

```C#
Задача 1
Напишите программу, которая на вход принимает два чиста и проверяет,
является ли первое число квадратом второго.
Console.WriteLine("Введите первое число: ");
int Nam1 = int.Parse(Console.ReadLine()!); // добавил !

Console.WriteLine("Введите второе число: ");
int Nam2 = int.Parse(Console.ReadLine()!); //int.Parse - конвертирование строки в тип int

if (Math.Pow(Nam2, 2) == Nam1)//Math - библиотека позволяющая работать с различными  математическими методами. Pow - степень
{
    Console.WriteLine("Первое число является квадратом второго!");

}
else
{
    Console.WriteLine("Первое число не является квадратом второго!");
}
```

>Можно выделить часть кода в строке. Для это в тексте сроки просто обрамите нужны фрагмент одни апострофом спереди и с сзади нужного фрагмента. Например:
>> Напечатаний текст, в котором `x=2`, что в данном контексте сомнительно)))

# Создание сносок:
>Для создания сносок используется следующий синтаксис:
>>Сноска первая \[^1] и сноска вторая \[^2]

Сноска первая [^1] и сноска вторая [^2]
>>далее мы пишем сам текст сноски,при чем сам текст сносок будет всегда находится внизу оформленного листа где бы вы его не составили в процессе оформления страницы.\
\[^1]: Текст сноски 1(Сноски всегда внизу файла, листа)\
\[^2]: Текст сноски 2(Сноски всегда внизу файла, листа)

[^1]: Текст сноски 1(Сноски всегда внизу файла, листа)

[^2]: Текст сноски 2(Сноски всегда внизу файла, листа)

# Создание таблиц:
> Синтаксис написания таблицы:\
\
Цвет | Количество | Размер\
:----|:-----------:|--------:\
красный | 1 | 256\
синий | 2 | 22\
зеленый | 5 | 6489


Цвет | Количество | Размер
:----|:-----------:|--------:
красный | 1 | 256
синий | 2 | 22
зеленый | 5 | 6489

# Создание списка определений:

>Синтаксис создания списка определений:\
Термин\
: Определение


Markdown (произносится маркда́ун)
: Облегчённый язык разметки, созданный с целью обозначения форматирования в простом тексте, с максимальным сохранением его читаемости человеком, и пригодный для машинного преобразования в языки для продвинутых публикаций (HTML, Rich Text и других).

>Что то не сработал список определений, вернусь позже к этому вопросу.

# Перехода вверх страницы по якорю:
>В строке 1 установил якорь \<a id="anchor"></a>, а последней строке тег на переход в первую сточку\[Вверх](#anchor).
>>Этим способом можно создать оглавление.


# Добавление картинки:
>Команда для добавления *картинки* или *гифки* выглядит следующим образом:
>>![Котик](вставить тут URL)


![Cat](https://c.tenor.com/NZqiUoAnAFsAAAAC/cat-computer.gif)

***
***
***

### P.S.: *И в заключении хотелось бы добавить, что все команды, то , как я оформил этот текст, в каждом знаке выше изложенного - заслуга моих преподавателей!!! Это* [Ильнар Шафигуллин](https://gb.ru/users/teachers/3546003 "Преподаватель GeekBrains") *человек умеющий* ***"красиво разложить"*** *и* ***"грамотно преподать"***. *И* [Софья Главацкая](https://gb.ru/users/teachers/7524512 "Преподаватель GeekBrains")-*покорившая своей ***добротой, умением слушать, терпением*** в помощи нам, задающим иногда глупые вопросы, студентам* [GeekBrains](https://gb.ru "IT-образование"). ***Спасибо!!!***

![Git](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQGtIP9OfwS0NgRXqpnxBVYHJuKStUiw9uLQg&usqp=CAU)


## P.S.: ***Продолжение следует...***
[Вверх](#anchor)