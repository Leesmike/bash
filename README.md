# Работа с bash

Работа в интерфейсе командной строки с выполнением базовых bash команд, таких как: 
- создание, перемещение и удаление файлов и каталогов
- редактирование, поиск и вывод информации из файлов и каталогов
- сетевые команды

---

- [TXT файл с задачей №1](https://github.com/Leesmike/git_bash/blob/main/bash1.txt), содержащей использование базовых команд bash для работы с файлами и каталогами (cd, mkdir, touch, ls, rm, echo, cat, nano)
- [TXT файл с задачей №2](https://github.com/Leesmike/git_bash/blob/main/bash2.txt), содержащей использование базовых команд bash для поиска, редактирования и вывода информации в файлах и каталогах, а также сетевые команды (grep, find, sed, ps, ping, curl)

---

## Задача №1

```bash
#Открыть домашнюю директорию через терминал:
cd

#Определить имя папки, в которой вы находитесь:
pwd

#Создать внутри этой папки каталог с именем test1:
mkdir test1

#Перейти в папку test1:
cd test1

#Создать файл 1,2 и 3 внутри каталога test1:
touch file1.txt file2.txt file3.txt

#Проверить содержимое каталога test1:
ls -la

#Перейти в домашнюю директорию:
cd ~

#Создать папку test2 внутри домашней директории:
mkdir test2

#Удалить папку test2:
rmdir test2

#Удалить файл 2 из папки test1:
rm ~/test1/file2.txt

#Создать папку в домашней директории test3 и добавить в нее два файла:
mkdir ~/test3
touch ~/test3/file1.txt ~/test3/file2.txt

#Удалить папку test3:
rm -r ~/test3

#Создать папку test4 в домашней директории:
mkdir ~/test4

#Переместить файлы 1 и 3 из папки test1 в папку test4:
mv ~/test1/file1.txt ~/test1/file3.txt ~/test4

#Добавить в файл 1 три строки со словами line:
echo line1 >> ~/test4/file1.txt
echo line2 >> ~/test4/file1.txt
echo line3 >> ~/test4/file1.txt

#Посмотреть содержимое файла 1:
cat ~/test4/file1.txt

#Добавить в файл 3 три строки со словами line:
echo line4 >> ~/test4/file3.txt
echo line5 >> ~/test4/file3.txt
echo line6 >> ~/test4/file3.txt

#Просмотреть содержимое двух файлов (1 и 3) сразу:
cat ~/test4/file1.txt ~/test4/file3.txt

#Используя один из редакторов заменить все строки в файле 1:
vim ~/test4/file1.txt, change lines, esc :wq
nano ~/test4/file1.txt, change lines, ctrl X
```

---

## Задача №2

```bash
#Зайти в домашнюю директорию через терминал:
cd ~

#Создать папку test 3:
mkdir test3

#Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4:
cd test3
echo -e "row1\nrow2\nrow3\nrow4" > file4.txt
echo -e "row1\nrow2\nrow3\nrow4" > file5.txt
echo -e "row1\nrow2\nrow3\nrow4" > file6.txt

#Найти строку row2 в файле 5:
grep -i "row2" file5.txt

#Найти строку row в папке test3:
grep -ri "row"

#Посчитать сколько строк с содержимым row в файле 6:
grep -c "row" file6.txt

#Найти файл 5 внутри папки test3:
find -name "file5.txt"

#Используя команду find, удалить файл 5:
find -name "file5.txt" -exec rm {} \;

#Используя команду echo, добавить слово test в файл 4:
echo test >> file4.txt

#Заменить слово test в файле 4 на fail:
sed -i 's/test/fail/g' file4.txt

#Добавить в файл 4 слово test так, чтобы сохранилось содержимое:
echo test >> file4.txt

#Просмотреть все процессы для юзеров не только в консоли, которые происходят в системе:
ps aux

#Убить процесс 666 в консоли:
kill 666

#Узнать доступность ресурса rusau.net, используя ping:
ping rusau.net

#Отправить 5 пакетов на сайт rusau.net:
ping -n 5 rusau.net или же ping -c 5 rusau.net (в зависимости от используемой системы)

#Используя GET и команду curl, получить информацию о зарегистрированных питомцах с любым статусом на https://petstore.swagger.io/:
curl -X GET https://petstore.swagger.io/v2/pet/findByStatus?status=sold

#Используя POST и команду curl, создать нового пользователя на https://petstore.swagger.io/:
curl -X POST https://petstore.swagger.io/v2/user -H "Content-Type: application/json" -d '{"id": 42999, "username": "PAD", "firstName": "Sakuya", "lastName": "Izayoi", "email": "scarlet@mist.rem", "password": "remilia123", "phone": "213", "userStatus": 1}'
```
