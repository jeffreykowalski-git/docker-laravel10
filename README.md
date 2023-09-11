# docker-laravel10
A Docker LEMP build including Laravel 10, MySQL, Nginx, PHP, NPM, Composer, and Artisan ready to go.

## Installation

Install Docker Desktop locally https://docs.docker.com/engine/install/

Then from terminal in your project folder root run the following commands.
These will install your mysql container, node_modules, and create/migrate your db respectively.
You will need two terminal windows open as the first command will start the nginx
server and keep listening on port 80.

`docker-compose up --build`

From second terminal:

`docker-compose run --rm npm install`

Change file `.env.example` to `.env` in `/src` folder

`docker-compose run --rm artisan migrate`

After initial install you can stop the container by either **Cntrl-C** to escape.
Or by using the *Docker-Desktop* GUI.

## Working folder
The working *Laravel* folder is `/src`. Do all your development here.

## Starting container after install/exit

`docker-compose up`


## Usage examples

Run your normal development commands from within the project root folder while container is running.

### Install composer package
`docker-compose run --rm composer require {package}/{packagename}`

### Dump Autoload
`docker-compose run --rm composer dump-autoload`

### Build assets
`docker-compose run --rm npm run dev`

### Make model with migration etc.
`docker-compose run -rm artisan make:model {ModelName} --migration`

## Credits
Modified from **The Docker Tutorial** on https://laracasts.com by Andrew Schmelyun, with many thanks.

