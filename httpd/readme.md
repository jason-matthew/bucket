# Overview

Establish HTTPD docker image which indexes file system and acts as a reverse proxy for other web applications.  Shared disk volume between `DocumentRoot` and other containers grants access to file system content.  

HTTPD configuration summary:

* custom `LogFormat` writes structured data
* `Options +Indexes` enabled for entire `DocumentRoot`
* subdomain traffic proxied to locally hosted containers (reference: [subdomains.conf](./assets/config/sites-enabled/subdomains.conf))
* Unregistered subdomain traffic rejected (404)

## Usage

`docker-compose` can be used to deploy HTTPD and additional web applications within a docker network.  See project [readme.md](../readme.md).  

## References

Apache Documentation

* [Directory Indexing](https://cwiki.apache.org/confluence/display/HTTPD/DirectoryListings)
* [Virtual Host introduction](https://httpd.apache.org/docs/2.4/vhosts/)
* [Virtual Host details](https://httpd.apache.org/docs/2.4/vhosts/details.html)

Misc: 

* (serverfault) [conf file complexities](https://serverfault.com/a/377494)
