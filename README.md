# Git clone

copy repo in your local directory:

`git colne https://github.com/dev-scripts/dockerize-react-app.git`

## Go inside 
Go into the project folder:

`cd dockerize-react-app`

## `docker compose build`
This command will take few minutes to 
pull the node image, install dependencies, copy files, and create app image.

## `docker compose up`
Now, you can run `docker compose up` command. This command will start the container and 
maps internal port `80` to external port `1111`.

You can also change the port number from `docker-compose.yml` file