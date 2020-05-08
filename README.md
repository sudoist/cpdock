# Cpdock

Cpdock is an easy setup of ClassicPress with Docker using Laradock for setting up nginx and mysql/mariadb containers.

[Based on the composer install with Bedrock.](https://docs.classicpress.net/installing-classicpress/installing-with-composer/#after-installation)

The goal is to have a development environment by running a few commands.

## Requirements

* Git

* Docker [ >= 17.12 ]

## Installation

1. Clone cpdock on your desired work directory:
    ```
    git clone https://github.com/sudoist/cpdock.git your-classicpress-site

    ```
2. cd into the project directory:
    ```
    cd your-classicpress-site

    ```
3. Copy the .env-example to .env
    ```
    cp .env-example .env

    ```
4. Generate `.env` variables with Bedrock's [WordPress salts generator](https://roots.io/salts.html) then....

5. Update the last section variables in the `.env` with the values from generator.

6. cd into the Laradcok directory:
    ```
    cd laradock

    ```
7. Copy the .env-example to .env
    ```
    cp env-example .env

    ```
8. Run your server with nginx and mysql:
    ```
    docker-compose up -d nginx mysql

    ```
9. Login to Laradock workspace
    ```
    docker-compose exec --user=laradock workspace bash
    ```
10. Install dependencies with composer
    ```
    composer install
    ```
11. Access [localhost](http://localhost/) to start installation.
