# TWD Drupal Project
## [Based off of Composer template for Drupal Projects](https://github.com/drupal-composer/drupal-project)

This project template should provide a kickstart for managing your site
dependencies with [Composer](https://getcomposer.org/).

## Usage

First you need to [install composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).

> Note: The instructions below refer to the [global composer installation](https://getcomposer.org/doc/00-intro.md#globally).
You might need to replace `composer` with `php composer.phar` (or similar)
for your setup.

After that you can install the project:

```
composer install
```

With `composer require ...` you can download new dependencies to your
installation.

```
cd some-dir
composer require drupal/devel:~1.0
```

## Hosting

Configure a web server to the web directory within this project. WAMP or MAMP can be used to do this locally.

## Docker

This project contains docker configuration files to run the environment within multiple docker containers.

Run `sudo docker-compose up` to start the containers, then go to `http://0.0.0.0:80` to start.

Docker for Windows and Mac are known to have some performance issues with mounted volumes. Docker Sync is a third party ruby gem to deal with this issue. This project includes a Docker Sync configuration for Mac, but can easily be modified to work with Windows. Read about Docker Sync [here](http://docker-sync.io/)

When installing Drupal from the Docker image, use this database configuration:

* Database: drupal
* Username: drupal
* Password: drupal
* Host: mariadb


## What does the template do?

When installing the given `composer.json` some tasks are taken care of:

* Drupal will be installed in the `web`-directory.
* Autoloader is implemented to use the generated composer autoloader in `vendor/autoload.php`,
  instead of the one provided by Drupal (`web/vendor/autoload.php`).
* Modules (packages of type `drupal-module`) will be placed in `web/modules/contrib/`
* Theme (packages of type `drupal-theme`) will be placed in `web/themes/contrib/`
* Profiles (packages of type `drupal-profile`) will be placed in `web/profiles/contrib/`
* Creates default writable versions of `settings.php` and `services.yml`.
* Creates `web/sites/default/files`-directory.
* Latest version of drush is installed locally for use at `vendor/bin/drush`.
* Latest version of DrupalConsole is installed locally for use at `vendor/bin/drupal`.
