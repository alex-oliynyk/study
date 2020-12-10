## Lab_4: Робота з Docker

1. Для ознайомляння що таке Docker звернувся до документації.
2. Для перевірки чи докер встановлений і працює правильно на віртуальній машині запустив перевірку версії, виведення допомоги та тестовий імедж:
    ```bash
    docker -v
    docker -h
    docker run docker/whalesay cowsay Docker is fun
    ```
    - перенаправив вивід цих команд у файл `my_work.log` та закомітив його до репозиторію.
3. Ознайомився з документацією створення Dockfile.
4. Встановив базовий імедж використовуючи наступні команди:
    ```bash
    docker pull python:3.7-slim
    docker images
    docker inspect python:3.7-slim
    ```
5. Створив власний репозиторій на Docker Hub. Мій Docker-репозиторій: https://hub.docker.com/r/alexolink/study
6. Виконав білд Docker імеджа та завантажив його до репозиторію. Для цього використав такі команди:
    ```bash
    docker build -t alexolink/study:django .
    docker images
    dokcer push alexolink/study:django
    ```
7. Для запуску веб-сайту потрібно виконав команду:
    ```bash
    docker run -it --name=django --rm -p 8000:8000 alexolink/study:django
    ``` 
    - перейшов на адресу `http://127.0.0.1:8000` та переконався що мій веб-сайт працює;
8. Створив Dockerfile для програми моніторингу.
9. Виконав білд даного імеджа і дав йому тег monitoring:
    ```bash
    docker build -t alexolink/study:monitoring --file Dockerfile.monitoring . 
    docker images
    ``` 
10. Вивантажив імедж в репозиторій
    ```bash
    docker push alexolink/study:monitoring
    ```
11. Запустив два імеджі:
    ```bash
    sudo docker run -it --rm -p 8000:8000 alexolink/study:django
    sudo docker run --net=host --rm -it alexolink/study:monitoring
    ```
12. Виникли труднощі з використанням ключа --volume, тому довелося експортувати файли з контейнеру, після чого скопіював server.log до репозиторію:
    ```bash
    sudo docker export b5e868517bcf > /home/alex/monitoring.tar
    ```