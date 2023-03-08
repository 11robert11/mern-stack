# MERN-Stack with docker compose - (__WIP__)

## What is it
An example of how to create a portable mern stack project running with docker. 

## What **isn't** it
* A completly bundled development envioment

## How to run it
The only dependany needed to run your project is docker. 

### Running in "production" mode
```docker compose -f docker-compose-production.yml up --build --remove-orphans```
* react served from nginx
* only production packages

### Running in development mode
```docker compose -f docker-compose-development.yml up --build --remove-orphans```
* changes made on the fly without need for redeployment
    * express
        * Uses nodemon
        * Docker volume mapped to code
    * react
        * Run using react
        * Docker volume mapped to code

## How it works
The main diffrences between the docker compose config files is that the `docker-compose-production.yml` config copys files into built images and serves react from nginx while the `docker-compose-development.yml` config file creates binds to your code allowing for changes to be made in the running containers. The `docker-compose-development.yml` config also runs backend code with `nodemon` and runs react with `npm node start`, these allow for changes in code to be applyied without restarting the stack. Each config creates a mongo-db container that the backend is able to connect to.
The    The `docker-compose-development` config runs your backend with `nodemon` allowing you to make changes to 