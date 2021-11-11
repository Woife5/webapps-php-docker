# Webapps Docker Image

## Installation
1. Download and Install [Docker](https://www.docker.com/get-started "How to install docker")
2. Clone this git repository `git clone <repo>`
3. Create a folder called "app". The Symfony project will be installed in this folder.
4. Run `docker-compose up --bild` within `<repo>` to start the containers. Aditionally you can use the `-d` flag to make the containers run in the background.
5. Open the docker dashboard and go to "Containers/Apps".
6. Expand `webapps-docker` and open the cli of the `php` container.
7. In the newly opend terminal run `symfony new --full .` to crete a new symfony project.

When the command is finished and the project was created sucessfully you can `exit` the terminal again. You should now see the symfony files within the "app" folder.

You can now navigate to [localhost:3000](http://localhost:3000) to access your project.

## Usage
