# Docker image for running PHP on CI

 * Based on [phusion/baseimage-docker](https://github.com/phusion/baseimage-docker) (but thrown away everything what is not needed for CI)
 * PHP installed from [Ondrej Sury's Ubuntu PPA](https://launchpad.net/~ondrej/+archive/ubuntu/php) which contains almost any posiible package
 * NodeJS installed from [deb.nodesource.com 10.x](https://deb.nodesource.com/node_10.x)

## APT packages added

 * curl
 * git
 * mongodb-clients
 * mysql-client
 * nodejs
 * postgresql-client
 * redis-tools
 * unzip

## PHP packages installed

 * bcmath
 * bz2
 * cli
 * curl
 * gd
 * gmp
 * imap
 * intl
 * json
 * mbstring
 * mcrypt (before php 7.2)
 * mongodb
 * mysql
 * opcache
 * pgsql
 * readline
 * redis
 * soap
 * sodium (from php 7.1)
 * sqlite3
 * xml
 * zip

## NPM packages globally installed

 * grunt
 * gulp

## Composer packages globally installed

 * [composer](https://getcomposer.org/) (of course)
 * [hirak/prestissimo](https://github.com/hirak/prestissimo) which speeds up composer install
 * [jakub-onderka/php-parallel-lint](https://github.com/JakubOnderka/PHP-Parallel-Lint) which tests PHP syntax in parallel

## Cache dirs redirected

 * NPM: `/cache/npm`
 * Composer: `/cache/composer`

You may want to set `/cache` dir as Docker image volume for faster CI build.

## ENV variables changed/added

 * `$PATH`: added `~/.composer/vendor/bin`
 * `$COMPOSER_NO_INTERACTION`: set to `1`
 * `$COMPOSER_ALLOW_SUPERUSER`: set to `1`

## Tags (and PHP version) available for Docker

 * 5.6
 * 7.0
 * 7.1
 * 7.2
 * 7.3
 * 7.4
