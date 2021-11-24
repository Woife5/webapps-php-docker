# Webapps PHP Docker Image

## Docker Image Installation
Download and Install [Docker](https://www.docker.com/get-started "How to install docker") if you do not already have it.

To use this image on Windows you will need to have WSL 2 installed. The docker installer will help you set it up.

1. Make sure docker is running. If not just open the Docker Desktop application (Docker Dashboard).
2. Clone this git repository `git clone https://github.com/Woife5/webapps-php-docker.git`
3. Create a folder called "app" and another folder called "mysql". The Symfony project will be installed in the "app" folder, the database files will be saved to the "mysql" folder. Additionally you may want to change the default git name and email in [the Dockerfile](./php/Dockerfile) to your name and email.
4. Run `docker-compose up --build` within `webapps-php-docker` to start the containers. As soon as you see something like the following message, the installation is done and you can move to the next step:

![Docker installation is ready](https://i.ibb.co/yRPBYvs/Container-Ready.png)

### Creating an empty symfony project
5. Open the docker dashboard and go to "Containers/Apps".
6. Expand `webapps-php-docker` and open the cli of the `php` container: ![Docker Dashboard](https://i.ibb.co/tHnMqr4/dockerdashboard.png)
7. In the newly opend terminal run `symfony new --full .` to crete a new symfony project: ![Terminal Window](https://i.ibb.co/PMH8tmg/dockerterminal.png)

When the command is finished and the project was created sucessfully you can `exit` the terminal again. You should now see the symfony files within the "app" folder.

You can now edit the files in the "app" folder and the changes should automatically be reflected in the docker container and the web server. 

You can now navigate to [localhost:3000](http://localhost:3000) to access your project.

The default user and password for the database are "root:root". You can change this in the docker-compose.yml file.

## Starting the image
Start the Docker image by running ```docker-compose up``` within the `webapps-php-docker` folder. You can use the `-d` flag to start the containers in the background.

After the fist time you can also start the image by opening the docker dashboard and starting it via the "Containers/Apps" tab and clicking on the Play-button next to the `webapps-php-docker` app.

When the containers are finished starting up, your project should be accessible at [localhost:3000](http://localhost:3000).

## Stopping the image
To stop the containers run ```docker-compose stop``` if you started the container with the `-d` flag or just push ```ctrl + c``` in the terminal that is running the containers.

You can also stop the containers via the docker dashboard by going to the "Containers/Apps" tab and clicking on the Stop-button next to the `webapps-php-docker` app.


## Database connection
To connect your symfony project to the database you need to edit the `.env` file within your "app" folder. There should be a line like this:

```DATABASE_URL="mysql://db_user:db_password@127.0.0.1:3306/db_name?serverVersion=5.7"```

You need to uncomment this line and comment out all other lines starting with `DATABASE_URL`. Afterwards you can edit this line to meet your settings, the default settings using this image are:

```DATABASE_URL="mysql://root:root@database:3306/db_name?serverVersion=5.7"```

`database` is the name of the container running the MySQL database. Docker will automatically map it to the correct container. The default version of the database is 5.7, however you can change this in the docker-compose file.

You can interact with the database directly by opening the CLI (command line interface) of the `database` container. Refert to the [MySQL Documentation](https://dev.mysql.com/doc/refman/8.0/en/mysql.html) for more information about using the MySQL command line interface.
