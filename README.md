 OVH API client
================

A bash client for [OVH API](https://api.ovh.com).

Dependencies
----------

Depends on the following executables
(might need manual installation):

  - [`jq`](https://stedolan.github.io/jq)
  - [`curl`](https://curl.haxx.se)
  - [`bash`](https://www.gnu.org/software/bash)

Depends on the following core utilities
(likely to be installed by default on most GNU/Linux distributions):

  - [`tr`](http://man7.org/linux/man-pages/man1/tr.1.html)
  - [`readlink`](http://man7.org/linux/man-pages/man1/readlink.1.html)
  - [`cat`](http://man7.org/linux/man-pages/man1/cat.1.html)
  - [`date`](http://man7.org/linux/man-pages/man1/date.1.html)
  - [`sha1sum`](http://man7.org/linux/man-pages/man1/sha1sum.1.html)
  - [`cut`](http://man7.org/linux/man-pages/man1/cut.1.html)


Initialize
----------

### Install

To install, run:

    make DESTDIR=/ PREFIX=/usr install

### Create an OVH API Application

In order to create a new OVH API application, run:

    ovh-api-client --initApp

### Create a Consumer Key

In order to create a new consumer key, run:

    ovh-api-client --init

Options
-------

### Show help

    ovh-api-client --help

Possible arguments are:
```
  --url <url>             : the API URL to call, for example /domains (default is /me)
  --method <method>       : the HTTP method to use, for example POST (default is GET)
  --data <JSON data>      : the data body to send with the request
  --target <CA|EU>        : the target API (default is EU)
  --init                  : to initialize the consumer key, and manage custom access rules file
  --initApp               : to initialize the API application
  --list-profile          : list available profiles in ~/.config/ovh-api-client/profile directory
  --profile <value>
            * default : from ~/.config/ovh-api-client/profile directory
            * <dir>   : from ~/.config/ovh-api-client/profile/<dir> directory
```

Usage
-----

### Just some examples:

To make a basic call on GET /me just run:

    ovh-api-client

To retrieve your domain list, run:

    ovh-api-client --url "/domain"

To activate the monitoring on your dedicated server, run:

    ovh-api-client --method PUT --url "/dedicated/server/ns00000.ovh.net" --data '{"monitoring": true}'

To create a Consumer key for different account or usage (profile is created if missing)

    ovh-api-client --profile demo1 --init
    ovh-api-client --profile demo2 --init

Embedded lib for external scripts
---------------------------------

See **contrib/** directory
