# PHP

PHP (an acronym for PHP: Hypertext Preprocessor) is a scripting language that’s generally used in “server-side” web development.

## Supported PHP versions

| PHP version | Supported | Note | phpinfo<sup>1</sup> |
|:---: |: ------------- :| : ------- | : ------- : |
| PHP5.3 | ✕ | Not developed since 2014 | - |
| PHP5.4 | ✕ | Not developed since 2015 | - |
| PHP5.5 | ✕ | Not developed since 2014 | - |
| PHP5.6 | ✓ | Deprecated, not developed since 2019, upgrade ASAP to 7.X | [phpinfo](http://denver.nuclearserver.xyz/phpinfo56.html) |
| PHP7.0 | ✓ | Deprecated, not developed since 2019, upgrade ASAP to 7.4 or higher | [phpinfo](http://denver.nuclearserver.xyz/phpinfo70.html) |
| PHP7.1 | ✓ | Deprecated, not developed since 2019, upgrade ASAP to 7.4 or higher | [phpinfo](http://denver.nuclearserver.xyz/phpinfo71.html) |
| PHP7.2 | ✓ | Deprecated, not developed since 2020, upgrade ASAP to 7.4 or higher | [phpinfo](http://denver.nuclearserver.xyz/phpinfo72.html) |
| PHP7.3 | ✓ | Deprecated, not developed since 2021, upgrade ASAP to 7.4 or higher | [phpinfo](http://denver.nuclearserver.xyz/phpinfo73.html) |
| PHP7.4 | ✓ | Deprecated, not developed since 2022, upgrade ASAP to 8.2 or higher | [phpinfo](http://denver.nuclearserver.xyz/phpinfo74.html) |
| PHP8.0 | ✓ | Deprecated, not developed since 2023, upgrade ASAP to 8.2 or higher | [phpinfo](http://denver.nuclearserver.xyz/phpinfo80.html) |
| PHP8.1 | ✓ | Recommended for production usage | [phpinfo](http://denver.nuclearserver.xyz/phpinfo81.html) |
| PHP8.2 | ✓ | Recommended for production usage | [phpinfo](http://denver.nuclearserver.xyz/phpinfo82.html) |
| PHP8.3 | ✓ | Recommended for production usage | [phpinfo](http://denver.nuclearserver.xyz/phpinfo83.html) |

<br />

!!! important
	We highly suggest you to always using newest PHP version for your website. Besides permormance reasons (newer PHP version has much more higher performance and radically can speed-up your website loading time), its security reasons and support from developers. Older PHP versions are hard to carry on on newest operating systems with latest upgrades.

!!! important
	PHP versions 5.6, 7.0, 7.1, 7.2, 7.3 are obsolete and no (or security) updates are released. We do not recommend using them, instead use one of the newer versions.

(1)Not all values in the example phpinfo must match the production environment. Some values differ for VIP and Basic Membership.

All PHP versions are available on all servers at all web hostings. There is no need to ask us to activate or move to another server. All you have to do is switch the version in the [Hosting Control Panel](https://my.nuclear.hosting).

## PHP Parameters

In the table, you can find a selection of some most-used PHP parameters configuration on our servers. The full list of all PHP directives can be found in phpinfo() function. Some values differ between Basic and VIP membership.

| PHP Directive | NH Basic Membership | NH VIP Membership |
| --- | ------------- | ------- |
| Number of PHP processes per domain | 4 | 10 |
| PHP memory_limit | 128MB | 256MB |
| PHP upload_max_filesize | 32MB | 256MB |
| PHP post_max_size | 40MB | 280MB |
| PHP max_execution_time | 30 | 300 |
| PHP allow_url_fopen | on | on |
| PHP max_input_vars | 2000 | 10000 |
| PHP default_socket_timeout | 60 | 60 |
| PHP short_open_tag | on | on |


### The list of installed PHP extensions

  - apcu
  - bcmath
  - bzip2
  - calendar
  - ctype
  - curl
  - date
  - dom
  - enchant
  - ereg
  - exif
  - fileinfo
  - filter
  - ftp
  - gmp
  - gd
  - geoip
  - gettext
  - hash
  - iconv
  - igbinary
  - imagick
  - imap
  - intl
  - ionCube Loader
  - json
  - libxml
  - mbstring
  - mcrypt
  - memcache
  - memcached
  - mhash
  - msgpack
  - mysqli, mysqlnd
  - openssl
  - pcntl
  - pcre
  - PDO (mysql, sqlite, pgsql)
  - pgsql
  - phar
  - pspell
  - readline
  - session
  - SimpleXML
  - soap
  - sockets
  - SPL
  - sqlite3
  - tidy
  - tokenizer
  - xml
  - xmlreader, xmlwriter
  - xmlrpc
  - xsl
  - opcache
  - zip
  - zlib

You can also use the PEAR extensions. You can upload it to your web hosting. These are basically "normal" PHP files/scripts. You can upload them to the web hosting via FTP, or set the right path for automatic inclusion in your app.

## How to change a PHP version for a website

Every hosting / website can use different PHP versions (within supported PHP versions). The change PHP version for a specific hosting you is simple from[Hosting Control Panel](https://my.nuclear.hosting).

In your [Hosting Control Panel](https://my.nuclear.hosting) navigate to ```Sites``` and click on the website where you want to change PHP version on. In the ```PHP Version``` select a version you want to use and just click on the ```Save``` button.

!!! note
	Your website has to be prepared and support your chosen PHP. Eg. application made for PHP5.6 will not work with PHP7.4 probably. Before changing PHP version make sure your application is prepared.