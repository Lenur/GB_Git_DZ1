# Инструкция для работы с Git и удалёнными репозиториями

## Что такое Git?
Git - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.
## Подготовка репозитория
Для создание репозитория необходимо выполнить команду *git init*  в папке с репозиторием и у Вас создаться репозиторий (появится скрытая папка .git)

## Создание коммитов

### Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите *git add <имя файла>*

### Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с пепозиторием следующим образом: *git checkout <номер коммита>*

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием

## Ветки в Git

### Создание ветки

Для того, чтобы создать ветку, используется команда *git branch*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*

## Слияние веток

Для того чтобы дабавить ветку в текущую ветку используется команда *git merge <name branch>*

## Удаление веток
Для удаления ветки ввести команду "git branch -d 'name branch'"

## Отмена изменений
Команда git reset, как можно догадаться из названия, используется в основном для отмены изменений. Она изменяет указатель HEAD и, опционально, состояние индекса.
Команда **git reset** имееет три режима:
* ***git reset: --soft***;
* ***git reset: --mixed***;
* ***git reset: --hard***.
<<<<<<< HEAD
## **git reset --soft**
Возьмем для примера ветку:
A - B - C (master)
HEAD указывает на C и индекс совпадает с C.
После выполнения: git reset --soft B
HEAD будет указывать на B и изменения из коммита C будут в индексе, как будто вы их добавили командой git add. Если вы сейчас выполните git commit вы получите коммит полностью идентичный C.
## **git reset --mixed (по умолчанию)**
Режим --mixed используется по умолчанию, т.е. git reset --mixed = git reset
Вернемся к тем же начальным условиям:
A - B - C (master)
Выполнив: git reset --mixed B или git reset B
HEAD опять же будет указывать на B, но на этот раз изменения из С не будут в индексе и если вы запустите здесь git commit ничего не произойдет т.к. ничего нет в индексе. У нас есть все изменения из С, но если запустить git status то вы увидите, что все изменения not staged. Чтобы их закоммитить нужно сначала добавить их в индекс командой git add и только после этого git commit.
## **git reset --hard**
Те же самые начальные условия:
A - B - C (master)
Последний режим --hard также как и --mixed переместит HEAD на В и очистит индекс, но в отличие от --mixed жесткий reset изменит файлы в вашей рабочей директории.
Если выполнить: git reset --hard B
то изменения из С, равно как и незакоммиченные изменения, будут удалены и файлы в репозитории будут совпадать с B. Учитывая то, что этот режим подразумевает потерю изменений, вы всегда должны проверять git status перед тем как выполнить жесткий reset чтобы убедиться что нет незакоммиченных изменений (или они не нужны).


### ***Сравнительная таблица режимов git reset:***

|            | меняет индекс | меняет файлы в рабочей директории | нужно быть внимательным |
|------------|:-------------:|:---------------------------------:|------------------------:|
|reset --soft|	нет          |	нет                              |	нет                    |
|reset [--mixed]|	да       |	нет                              |	нет                    |
|reset --hard|	да           |	да                               |	да                     |


## Pull request
Pull request — это заявка на слияние кода из разных веток. В процессе слияния Git создаст коммит и покажет все изменения в файле кода: добавленные до разветвления строки подсветятся зеленым цветом, удаленные — красным.

Зачем нужен pull-request:

1. Обсуждение с коллегами
2. Работа с комментариями
3. Выполнение  code-review
4. Автоматическое тестирование


## Цитаты из книги **Pro Git**
>Git хранит данные не как последовательность изменений или дельт, 
>а как последовательность снимков состояния (snapshot).

>Для всего, что сохраняется в Git, 
>сначала вычисляется контрольная сумма, 
>и в дальнейшем она же и используется для поиска содержимого.

***[Моя ссылка на GitHub](https://github.com/Lenur/ 'Мой GitHub')***

Моя почта: <blef07@gmail.com>
