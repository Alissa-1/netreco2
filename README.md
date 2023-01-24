# Инструкция по запуску
### 1. Предусловия
Для запуска проекта требуются установленные Git, JDK 11, IntelliJ IDEA, Docker

1. Склонировать репозиторий командой git clone
2. Запустить Docker Desktop
3. Запустить IntelliJ IDEA и открыть проект qa-diplom

### 2. Запуск контейнеров
Для старта контейнеров с БД (MySQL, PostgreSQL) и симулятором банковских сервисов выполнить в терминале команду docker-compose up

### 3. Запуск SUT
В новой вкладке терминала из корня проекта выполнить одну из команд:

**С подключением к MySQL:** java -jar artifacts\aqa-shop.jar --spring.datasource.url=jdbc:mysql://localhost:3306/app

**С подключением к PostgreSQL:** java -jar artifacts\aqa-shop.jar --spring.datasource.url=jdbc:postgresql://localhost:5432/app

### 4. Запуск авто-тестов
В консоли «Run Anything» (двойное нажатие Ctrl) выполнить одну из команд в зависимости от выбранной БД:

**С подключением к MySQL:** ./gradlew clean test -Ddb.url=jdbc:mysql://localhost:3306/app

**С подключением к PostgreSQL:** ./gradlew clean test -Ddb.url=jdbc:postgresql://localhost:5432/app

# Для получения отчета (Allure) использовать команду gradlew allureServe
