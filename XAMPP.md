# xampp

## wildcard domain

htdocs/projects/folder => http://folder.localhost

    create folder "projects" in xampp/htdocs/

edit xampp/apache/conf/extra/httpd-vhosts.conf

    UseCanonicalName Off

    <VirtualHost *:80>
       DocumentRoot "C:/xampp/htdocs/"
       ServerName localhost
    </VirtualHost>

    <VirtualHost *:80>
       ServerAlias *.localhost
       VirtualDocumentRoot "C:/xampp/htdocs/projects/%1/"
    </VirtualHost>

httpd.conf - uncomment the following module

    LoadModule vhost_alias_module modules/mod_vhost_alias.so

## xdebug

https://gist.github.com/odan/1abe76d373a9cbb15bed

xdebug downloads: https://xdebug.org/download.php

download the .dll (e.g. php_xdebug-2.6.0-7.2-vc15.dll ) for php version 7.2

    save .dll to xampp/php/ext/

edit xampp/php/php.ini

    output_buffering = Off

Scroll down to the [XDebug] section (or create it) and copy this lines:

    [XDebug]
    zend_extension = "c:\xampp\php\ext\php_xdebug-2.6.0-7.2-vc15.dll"
    xdebug.remote_autostart = 1
    xdebug.profiler_append = 0
    xdebug.profiler_enable = 0
    xdebug.profiler_enable_trigger = 0
    xdebug.profiler_output_dir = "c:\xampp\tmp"
    ;xdebug.profiler_output_name = "cachegrind.out.%t-%s"
    xdebug.remote_enable = 1
    xdebug.remote_handler = "dbgp"
    xdebug.remote_host = "127.0.0.1"
    xdebug.remote_log = "c:\xampp\tmp\xdebug.txt"
    xdebug.remote_port = 9000
    xdebug.trace_output_dir = "c:\xampp\tmp"
    ;36000 = 10h
    xdebug.remote_cookie_expire_time = 36000

