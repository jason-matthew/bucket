# Overview

HTTPD used to manage ingress to other docker containers and grant access to generated content.  

The current location serves HTTPD DocumentRoot and allows uses to navigate directory structure.  Specific applications can establish volumes within `/usr/local/apache2/htdocs/` to enable direct file access.