# Bedrock Docker Dev

> Used the Cpdock repo as a base for Bedrock project.
> Same installation steps.

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
4. Generate and copy `.env` variables with Bedrock's [WordPress salts generator](https://roots.io/salts.html) then....

5. Update the last section variables in the `.env` with the values from generator using your favorite text editor or IDE.

    ```
    # For example in my system with terminal.

    featherpad .env
    ```
6. cd into the Laradock directory:
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
    docker-compose exec --user=laradock workspace bash // If getting permission errors, simply run as root by entering command below
    ```
    ```
    docker-compose exec workspace bash // We only need to install composer
    ```
10. Install dependencies with composer
    ```
    composer install
    ```
11. Access [localhost](http://localhost/) to start installation.

# Ecommerce plugins

## [Classic Commerce](https://classiccommerce.cc/)

> The Classic Commerce project was initiated in the early stages of the ClassicPress development process, when it became clear that a reliable e-commerce solution would be a necessity.

> ClassicPress was promoting itself as the "business-focused CMS" and a dependable, secure and independent e-commerce plugin is obviously one of the basic requirements for the business community.

If you would like to install Classic Commerce run these composer command instead of the one in step 10: 

    env COMPOSER=composer-cc.json composer install

Thanks to Classic Commerce community for helping with configuration to install with [composer](https://github.com/ClassicPress-research/classic-commerce/issues/239).

## Based on Laradock and Bedrock

### Laradock

This project is based on awesome [Laradock](https://github.com/laradock/laradock).

### Bedrock

A WordPress boilerplate for setting up new projects with modern tools.

[Bedrock](https://roots.io/bedrock/) works smoothly with ClassicPress installation.

## Enjoy creating your new awesome site.
