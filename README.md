Домашнее задание #1 на тему Git Bash  
Ознакомление с terminal и расширенное описание выполняемых команд

## 1. Посмотреть где я
Для того чтобы увидеть в каком катоалогке мы накходимся используется команда `pwd`
```
$ pwd
/c/Users/nikol
```

## 2. Создать папку
Создадим каталог **HWterminal1**, для этого используем команду `mkdir имя_каталога`
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~
$ mkdir HWterminal1
```
## 3. Зайти в папку
Чтобы зайти в каталог используем `cd имя_каталога` 
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~
$ cd HWterminal1
```

## 4. Создать 3 папки
Создадим три каталога c с помощью команды `mkdir`. Для создания нескольких каталогов название разделим пробелом.
```
$ mkdir folder1 folder2 folder3
```

## 5. Зайти в любую папку
Перейти в каталог **folder1**
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1
$ cd folder1
```
## 6. Создать 5 файлов (3 .txt, 2 .json)
Для того чтобы создать пустой файл используется команду `touch`
```
$ touch имя_файла.расширение
```
Для создания сразу несколько файлов, воспользуемся пробелами между файлами.
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1/folder1
$ touch one.txt two.txt three.txt jone.json jtwo.json
```
## 7. Создать 3 папки
Создаём 3 подкаталога с именами в каталоге **folder1**
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1
$  mkdir folder1 folder2 folder3
```
## 8. Вывести список содержимого папки
`ls` команда для того чтобы вывести содержимое текущего каталога
+ `ls -la` — отображает расширенную информацию о файлах и папках.
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1/folder1
$ ls
directory1/  directory3/  jtwo.json  three.txt
directory2/  jone.json    one.txt    two.txt
```

## 9-11. Открыть .txt файл, написать туда любой текст, сохранить и выйти
Для того чтобы открыть и начать редактировать файл можно воспользоваться командой `cat >`   

```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1/folder1
$ cat > one.txt
```
После этого мы можем редактировать файл и добавлять в него любой текст.  

```
one
two
three
four
five
six
seven

```
Для того чтобы сохранить и выйти из редактирования используем сочетание клавиш `Ctrl` + `D`

## 12. Выйти из папки на уровень выше
Команды для навигации `cd`:
+ `cd  ` — без параметров перемещает в домашнюю директорию пользователя,
+ `cd .` — текущая директория,
+ `cd ..` — родительская директория,
+ `cd ~`  — домашняя директория пользователя.

Перейти на уорвень выше `cd ..`
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1/folder1
$ cd ..
```
## 13. Переместить любые 2 файла, которые вы создали, в любую другую папку.
Для перемещения файлов используют команду `mv`:
```
$ mv файл(-ы) путь
```
Переместим файлы **one.txt** и **two.txt** из каталога **folder1** в **folder2**
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1
$ mv folder1/{one.txt,two.txt} folder2
```

## 14. Скопировать любые 2 файла, которые вы создали, в любую другую папку.
Для копирования файлов используют команду `cp`, синтаксис :
```
$ cp файл(-ы) путь
```
Скопируем  ту же файлы **one.txt** и **two.txt** из каталога **folder2** в **folder3**
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1
$ cp folder2/one.txt folder2/two.txt folder3
```
## 15. Найти файл по имени
Для поиска используется команда `find`, синтаксис :
```
find место_поиска ключ-свойство значение_свойства
```
+ `find -name "шаблон"` — находит файлы с именами, соответствующими шаблону,

Найдём для примера путь до файла **one.txt** используя маску "one*"
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1
$ find -name "one*"
./folder2/one.txt
./folder3/one.txt


```
## 16. Просмотреть содержимое в реальном времени (команда `grep`) изучите как она работает.
### Команда `tail`
Часто для просмотра файла, когда не обязательно видеть всё содержимое, например для логов, используется команда `tail`, которая позволяет посмотреть что находится в части файла. С ней так же можно совместно использовать `grep`
```
$ tail | grep ""
```
+ `tail -n 5` — выведет последние 5 строк,
+ `tail -f` — будет выводить строки в реальном времени, по мере обновления файла,
 

Чтобы отследить обновления в файле используем команду `tail -f`
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1
$ tail -f ./folder3/one.txt
```
```
one
two
three
four
five
six
seven

```
 Добавим новые строки с помощью текстовго редактора в файл **one.txt** и сохраним результат `Ctrl`+`S` 
```
red
green
blue
``` 
Информация в терминале обновится:
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1
$ tail -f ./folder3/one.txt
one
two
three
four
five
six
seven
red
green
```

Для выхода  `Ctrl`+`C`

---
### Команда `grep` 
Команда позволяющая выполнять поиск внутри содержимого файла по различным параметрам Команда grep имеет огромное количество опций и вариантов использования.
```
grep — команда
[опции] — модификаторы команды
значение — поисковый запрос
[ФАЙЛ] — файл, в котором вы выполняете поиск
```

Можно просмотреть документацию и пояснения к различным опциям команды, введя в командной строке:
```
grep –help
```
наиболее важными и часто используемыми являются параметры:
```
-i — поиск не будет чувствителен к регистру. То есть, если вы хотите найти слово «автомобиль», написанные как «АВТОМОБИЛЬ» слова тоже будут найдены.
-c — покажет только количество строк, содержащих поисковый запрос
-r — включает рекурсивный поиск в текущем каталоге
-n — выведет номера строк, содержащих поисковый запрос
-v — обратный поиск, выводит только строки, в которых нет указанного поискового запроса
```


## 17. Вывести несколько первых строк из текстового файла
Для вывода первых строк используется команда `head`, синтаксис :
```
$ head опции файл
```
+ `head -n 5` — выведет первые 5 строк,
+ `head -c 250` — выведет указанное количество байт от начала файла.

Выведем первые 5 строк из файла **three.txt**
**
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1/folder1
$ head -n 5 three.txt

```
В результате получим строки.
```
У лукоморья дуб зелёный;
Златая цепь на дубе том:
И днём и ночью кот учёный
Всё ходит по цепи кругом;
Идёт направо — песнь заводит,
```

## 18. Вывести несколько последних строк из текстового файла
Для вывода последних строк используется команда `tail`, синтаксис :
```
$ tail опции файл
```
+ `tail -n 3` — выведет последние 3 строк,
+ `tail -f` — будет выводить строки в реальном времени, по мере обновления файла,
+ `tail -c 50` — выведет указанное количество байт с конца файла. 

Выведем последние 20 байт из файла **three.txt**
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1/folder1
$ tail -n 3 three.txt
```
В результате получим
```
Следы невиданных зверей;
Избушка там на курьих ножках
Стоит без окон, без дверей;
```

## 19. Просмотреть содержимое длинного файла (команда `less`) изучите как она работает.
Используем `less` для чтения содержимого длинного файла
```
$ less опции файл
```
+ `less -s` — заменит несколько идущих подряд пустых строк одной строкой,
+ `less -n` — не выводить номера строк,
+ `less -N` — вывести номера строк,
+ `less -i` — игнорировать регистр,
+ `less +f` — просматривать добавление строк в реальном времени,


## 20. Вывести дату и время  
Для вывода времени используем `date`
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal_1
$ date
```
```
Wed Apr 26 22:18:54     2023
```
=========

## *21. Отправить HTTP запрос на сервер.
Для того чтобы отправить запрос воспользуемся командой `curl` и методом `-X GET`
```
nikol@DESKTOP-A1PNQL6 MINGW64 ~/HWterminal1/folder1
$ curl -X GET http://162.55.220.72:5005/terminal-hw-request
```
Результатом выполнения запроса является ответ от сервера
```
    % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   232  100   232    0     0   1395      0 --:--:-- --:--:-- --:--:--  1397<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<title>404 Not Found</title>
<h1>Not Found</h1>
<p>The requested URL was not found on the server. If you entered the URL manually please check your spelling and try again.</p>
```
## *22. Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13
```
$ #!/bin/bash
cd HWterminal_1
mkdir folder1 folder2 folder3
cd folder1
touch one.txt two.txt three.txt jone.json jtwo.json
mkdir directory1 directory2 directory3
ls
cd ..
mv folder1/{one.txt,two.txt} folder2
directory1/  directory2/  directory3/  jone.json  jtwo.json  one.txt  three.txt  two.txt

```
