behat-rest-testing
==================

Repo demonstrating how to test a REST API with behat

# Dependencies

The [PECL HTTP](http://pecl.php.net/package/pecl_http) package is required. I recommend
googling how to install it for your environment as installation varies widely.

# Install

You will need to install composer first.

	#composer
	curl -s http://getcomposer.org/installer | php
	php composer.phar install

Now setup a vhost for foo.local pointing to the project's public dir. I'll go ahead and
include an example vhost below.

	<VirtualHost *:80>
		ServerName foo.local
		DocumentRoot /path/to/project/behat-rest-testing/public

		ErrorLog ${APACHE_LOG_DIR}/foo.local.error.log

		# Possible values include: debug, info, notice, warn, error, crit,
		# alert, emerg.
		LogLevel notice

		CustomLog ${APACHE_LOG_DIR}/foo.local.access.log combined
	</VirtualHost>

If you need more help with vhost setup checkout the [apache docs](http://httpd.apache.org/docs/2.0/vhosts/examples.html).


# Credits

This example is essentially a hard fork of https://github.com/enygma/behat-fuel-rest by Chris Cornutt.
Most of the code in RestContext.php is from that repo's FeatureContextRest.php refactored to be used as a sub context.
