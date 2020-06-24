#Устанавливаем базовый образ
FROM postgres:latest

#WORKDIR — задаёт рабочую директорию для следующей инструкции.
WORKDIR /

#ENV — устанавливает постоянные переменные среды. Тут мы задаем пароль, пользователя и бд.
ENV POSTGRES_PASSWORD postgres
ENV POSTGRES_USER postgres
ENV POSTGRES_DB name

#RUN — выполняет команду и создаёт слой образа. Тут мы создаем директорию для следующей команды
RUN mkdir --parents /docker-entrypoint-initdb.d

#COPY — копирует в контейнер файлы и папки. Все из папки pg-init-scripts в папку docker-entrypoint-initdb.d в контейнере.
COPY ./pg-init-scripts ./docker-entrypoint-initdb.d