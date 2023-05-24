# Docker-compose
# python-with-mysql-database

# 1. Manual Approch
# Pre-Requisites:

- Mysql Database Setup

- Install python, pip

# Mysql Database Setup
- Mysql SetUp

# Install required modules using below command

- pip install -r requirements.txt
# Run Application

- python application.py
# Open Port number 5000 with security group and check output with in WebUI
http://18.205.106.9:5000/insertemployee

http://18.205.106.9:5000/listofemployees

# 2. Docker Run Approch

# Docker Build

- docker build -t python-app:v1 .

- docker tag python-app:v1 naresh240/python-app:v1

- docker login

- docker push naresh240/python-app:v1

# Docker run commands:

- docker run --name mysqldb -p 3306:3306 -e MYSQL_ROOT_PASSWORD=Admin#123 -d mysql:5.7

- docker run --name python-app --link mysqldb -p 5000:5000 -d naresh240/python-app:v1

# 3. Docker compose Approch

- docker-compose up -d

- docker-compose down

# Docker Stack Deploy under swam

- docker stack deploy --compose-file python-stack.yml python-deploy

- docker network ls

- docker stack ls

- docker stack rm python-deploy
