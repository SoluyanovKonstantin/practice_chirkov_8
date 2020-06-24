# Практическая работа №8
ИТ-31 Солуянов
Платформа Windows 10 Home v.2004

1) Установить docker desktop [здесь](https://www.docker.com/get-started) и ввести в терминале `docker pull ubuntu` и `docker pull postgres`.
Для запуска образа нужно создать контейнер и запустить его, для этого можно либо ввести такую команду `winpty docker run -it <image_name>` либо такие `docker container create --name my_container <image_name>` `winpty docker container start -it <name_container>`. Команда run - сразу создает и запускает контейнер, во втором случае эти действия разделены, --name - необязательная опция которая задает имя контейнеру, иначе имя будет задано автоматически, -it - это 2 опции --interactive и --tty, дает возможность сразу после запуска давать команды контейнеру.

2) 
   - Создаем Dockerfile, он лежит в папке docker с комментариями.
   - Создаем образ командой `docker build --tag my_image .` --tag/-t - задает тэг для образа.
   - Cоздаем контейнер командой `docker container create --name my_container my_image`
   - Запускаем контейнер  `docker container start my_container`

3)
   - ```winpty docker exec -it my_container bash```
   - ```psql -h localhost -p 5432 -U postgres -W```
   - ```CREATE TABLE name_table (ID int primary key,Name text);```
   - ```insert into name_table values (1, 'Text');```
   - ```SELECT * FROM name_table;```
   - ```\q```
   - ```exit```
   - Cоздаем дамп ```docker exec -t my_container pg_dumpall -c -U postgres > ./pg-init-scripts/dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql```

4) Docker Compose устанавливается вместе с Docker desktop

5)
   - Перейти на директорию выше
   - Ввести `docker-compose -f docker-compose.yml up`
   - В браузере зайти на http://localhost:8080/
   - Выбрать движок PostgreSQL, имя пользователя postgres, пароль example, база данных postgres