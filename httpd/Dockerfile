FROM httpd:2.4
LABEL   name="bucket-httpd" \
        description="HTTPD subdomain proxy and directory index" \
        vcs-url="https://github.com/jason-matthew/bucket" \
        maintainer="Jon.Gates" \
        header="I can put custom content here too, right?"

# leverage local httpd conf files
RUN rm /usr/local/apache2/htdocs/index.html \
    && mkdir /usr/local/apache2/conf/sites-enabled \
    && echo 'Include /usr/local/apache2/conf/sites-enabled/*.conf' | tee -a /usr/local/apache2/conf/httpd.conf

# custom httpd configuration
COPY assets/config/sites-enabled/* /usr/local/apache2/conf/sites-enabled/

# custom HTML content
# COPY assets/html/* /usr/local/apache2/htdocs/

# spot-check HTTPD config
# (assumes httpd:2.4 does not introduce an entrypoint)
# -l : list compiled in modules
# -S : a synonym for -t -D DUMP_VHOSTS -D DUMP_RUN_CFG
# CMD ["httpd-foreground", "-S"]