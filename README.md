hypeJunctionPro Starter Project
===============================

This is a quickstart skeleton for building a site based on Elgg 3.x and hypeJunction Pro plugins


## Installation

```sh
## Add your Private Packagist credentials to global config
## You can find your username and token by logging into https://packagist.com/

composer config --global --auth http-basic.repo.packagist.com <username> <token>
```

```sh
## Create a new Elgg project with hypeJunction Pro plugins pre-installed

cd /path/to/root/

composer self-update

composer global require fxp/composer-asset-plugin

composer create-project hypejunction/hypejunction:dev-master ./project-name

composer install
composer install # 2nd call is currently required
```