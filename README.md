CreateBundleTest
================

A Symfony project created on April 16, 2018, 3:20 pm.

1. Take a git clone of the project from https://github.com/KhatanaVikas/createBundleTest.git
2. Add server details in "etc/apache2/sites-available" and register in "hosts"
    the file reads as follows:

    <VirtualHost *:80>
	# The ServerName directive sets the request scheme, hostname and port that
	# the server uses to identify itself. This is used when creating
	# redirection URLs. In the context of virtual hosts, the ServerName
	# specifies what hostname must appear in the request's Host: header to
	# match this virtual host. For the default virtual host (this file) this
	# value is not decisive as it is used as a last resort host regardless.
	# However, you must set it for any further virtual host explicitly.
	ServerName www.createbundletest.com
	ServerAlias createbundletest.com

	ServerAdmin vikas@localhost
	DocumentRoot /var/www/createBundleTest/web

	#ReWite Rule for Apache to redirect to home page

   <Directory /var/www/createBundleTest/web>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride None
        Order allow,deny
        allow from all
    </Directory>

	# Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
	# error, crit, alert, emerg.
	# It is also possible to configure the loglevel for particular
	# modules, e.g.
	#LogLevel info ssl:warn

	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined

	# For most configuration files from conf-available/, which are
	# enabled or disabled at a global level, it is possible to
	# include a line for only one particular virtual host. For example the
	# following line enables the CGI configuration for this host only
	# after it has been globally disabled with "a2disconf".
	#Include conf-available/serve-cgi-bin.conf
</VirtualHost>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet



3. Do a "a2ensite file name" and then "service apache2 reload".
4. Do a composer install finally.
5. Run the project at createbundletest.com/app_dev.php
6. do a chmod -R 777 app/cache/* app/logs/* for cache and log permissions