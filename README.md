# Docker base for Symfony 4.x with nginx, php 7.3, MySQL 5.7

## Configuration

* Configure environment variable for your usage in .env
* Create docker network for your project with command ```docker network create PROJECT_NAME``` (replace PROJECT_NAME by the value of your .env file)
* Add all files of this repository on your project directory (be careful to merge .env file if you have already one)

If you are on linux system :
* `sudo chmod 777 var/ -R`
* If not already started : `docker run -d --name docker-hostmanager --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /etc/hosts:/hosts d3tdistribution/docker-hostmanager`

The image and the container docker-hostmanager permit to you to access to your project with a "human" host. (ex: `http://my-project.docker/`)

On Mac OSX and Windows, you can access to your project on the "localhost" host on the port configure in .env for variable `WEBSERVER_PORT`. 

## Launch

* Execute ```docker-compose up -d``` (Images is building... wait... and containers is launching...)
* Execute your install command (ex : ```composer install``` inside the php container)
* Go to http://your-project.docker (for Linux user) or http://localhost:WEBSERVER_PORT for others (replace WEBSERVER_PORT by the value configure in .env)

