Docker Image Packaging for Apache
=================================

[![Travis](https://img.shields.io/travis/alvistack/docker-httpd.svg)](https://travis-ci.org/alvistack/docker-httpd)
[![GitHub release](https://img.shields.io/github/release/alvistack/docker-httpd.svg)](https://github.com/alvistack/docker-httpd/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/docker-httpd.svg)](https://github.com/alvistack/docker-httpd/blob/master/LICENSE)
[![Docker Pulls](https://img.shields.io/docker/pulls/alvistack/httpd.svg)](https://hub.docker.com/r/alvistack/httpd/)

The Apache HTTP Server Project is an effort to develop and maintain an open-source HTTP server for modern operating systems including UNIX and Windows. The goal of this project is to provide a secure, efficient and extensible server that provides HTTP services in sync with the current HTTP standards.

Learn more about Apache: <https://httpd.apache.org/>

Supported Tags and Respective `Dockerfile` Links
------------------------------------------------

-   [`latest` (master/Dockerfile)](https://github.com/alvistack/docker-httpd/blob/master/Dockerfile)
-   [`2.4` (2.4/Dockerfile)](https://github.com/alvistack/docker-httpd/blob/2.4/Dockerfile)

Overview
--------

This Docker container makes it easy to get an instance of Apache up and running.

Based on [Official Apache Docker Image](https://hub.docker.com/_/httpd/) with some minor hack:

-   Handle `ENTRYPOINT` with [dumb-init](https://github.com/Yelp/dumb-init)
-   Change `User` and `Group` to `www-data`
-   Change `DocumentRoot` to `/var/www/html`
-   Additional Apache modules:
    -   actions
    -   deflate
    -   expires
    -   logio
    -   mime\_magic
    -   negotiation
    -   proxy
    -   proxy\_fcgi
    -   proxy\_http
    -   remoteip
    -   rewrite

### Quick Start

For the `VOLUME` directory that is used to store the repository data (amongst other things) we recommend mounting a host directory as a [data volume](https://docs.docker.com/engine/tutorials/dockervolumes/#/data-volumes), or via a named volume if using a docker version &gt;= 1.9.

Start Apache:

    # Pull latest image
    docker pull alvistack/httpd

    # Run as detach
    docker run \
        -itd \
        --name httpd \
        --publish 80:80 \
        --volume /var/www/html:/var/www/html \
        alvistack/httpd

**Success**. Apache is now available on port <http://localhost>.

Versioning
----------

The `latest` tag matches the most recent version of this repository. Thus using `alvistack/httpd:latest` or `alvistack/httpd` will ensure you are running the most up to date version of this image.

License
-------

-   Code released under [Apache License 2.0](LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

