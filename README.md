# Dockerized Neos project boilerplate

This is an easy customizable Neos docker boilerplate based on the [TYPO3 docker boilerplate](https://github.com/webdevops/TYPO3-docker-boilerplate) by the awesome team webdevops.
It has some minor changes to have an optimized environment to use it with Neos instead of TYPO3.

[![latest v5.1.3](https://img.shields.io/badge/latest-v5.1.3-green.svg?style=flat)](https://github.com/webdevops/Neos-docker-boilerplate/releases/tag/5.1.3)
![License MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/webdevops/neos-docker-boilerplate.svg)](http://isitmaintained.com/project/webdevops/neos-docker-boilerplate "Average time to resolve an issue")
[![Percentage of issues still open](http://isitmaintained.com/badge/open/webdevops/neos-docker-boilerplate.svg)](http://isitmaintained.com/project/webdevops/neos-docker-boilerplate "Percentage of issues still open")

This is supposed to be used with [Dinghy](https://github.com/codekitchen/dinghy) as replacement for docker-machine
to make your life much easier.
You can also read about this in our [blogpost](http://blog.1drop.de/en/developing-neos-with-docker/).

Modifications made for Neos:

* Enable Ubuntu PHP7 as default app container (PHP7 in Debian is currently broken, see [this issue](https://github.com/gplessis/dotdeb-php/issues/124) on Github for details)
* Keep Flow Temporary inside the container to dramatically increase performance
* Modify nginx to deal with Flow
* Adapt internal host to dinghy default hostnames (*.docker)
* Set docker env variable for dinghy reverse proxy

## How to use it

    git clone https://github.com/webdevops/Neos-docker-boilerplate
    cd Neos-docker-boilerplate
    make create neos
    cp docker-compose.development.yml docker-compose.yml
    make up
    
After a few seconds your environment is ready and you can access it at http://neos.docker/setup

## Credentials

Database:

* User: dev
* Password: dev
* Database: neos
* Hostname: mysql
