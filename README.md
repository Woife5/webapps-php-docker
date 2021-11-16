# Webapps PHP Docker Image

## Docker Image Installation
Download and Install [Docker](https://www.docker.com/get-started "How to install docker") if you do not already have it.

To use this image on Windows you will need to have WSL 2 installed. The docker installer will help you set it up.

1. Make sure docker is running. If not just open the Docker Desktop application (Docker Dashboard).
2. Clone this git repository `git clone https://github.com/Woife5/webapps-php-docker.git`
3. Create a folder called "app". The Symfony project will be installed in this folder. Additionally you may want to change the default git name and email in `./php/Dockerfile` to your name and email.
4. Run `docker-compose up --build` within `webapps-php-docker` to start the containers. As soon as you see something like the following message, the installation is done and you can move to the next step:

![Docker installation is ready](https://i.ibb.co/yRPBYvs/Container-Ready.png)

### Creating an empty symfony project
5. Open the docker dashboard and go to "Containers/Apps".
6. Expand `webapps-php-docker` and open the cli of the `php` container: ![Docker Dashboard](https://i.ibb.co/tHnMqr4/dockerdashboard.png)
7. In the newly opend terminal run `symfony new --full .` to crete a new symfony project: ![Terminal Window](https://i.ibb.co/PMH8tmg/dockerterminal.png)

When the command is finished and the project was created sucessfully you can `exit` the terminal again. You should now see the symfony files within the "app" folder.

You can now edit the files in the "app" folder and the changes should automatically be reflected in the docker container and the web server. 

You can now navigate to [localhost:3000](http://localhost:3000) to access your project.

## Starting the image
Start the Docker image by running ```docker-compose up``` within the `webapps-php-docker` folder. You can use the `-d` flag to start the containers in the background.

After the fist time you can also start the image by opening the docker dashboard and starting it via the "Containers/Apps" tab and clicking on the Play-button next to the `webapps-php-docker` app.

When the containers are finished starting up, your project should be accessible at [localhost:3000](http://localhost:3000).

## Stopping the image
To stop the containers run ```docker-compose stop``` if you started the container with the `-d` flag or just push ```ctrl + c``` in the terminal that is running the containers.

You can also stop the containers via the docker dashboard by going to the "Containers/Apps" tab and clicking on the Stop-button next to the `webapps-php-docker` app.
