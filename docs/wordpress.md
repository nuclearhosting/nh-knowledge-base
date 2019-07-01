# Wordpress

WordPress is open source software you can use to create a beautiful website, blog, or app. Beautiful designs, powerful features, and the freedom to build anything you want. WordPress is both free and priceless at the same time.

## Installing Wordpress by 1-Click Installer

Installing a Wordpress to your domain on Nuclear.Hosting is such easy! You can install a new Wordpress directly from your [Hosting Control Panel account](https://my.nuclear.hosting) by one click! All installation is completed automatically and your Wordpress is ready tu use within minute.

To install Wordpress using 1-Click Installer log in to your [Hosting Control Panel account](https://my.nuclear.hosting) and click on the ```1-Click Apps``` located on the top menu.

Continue by clicking on ```Install Wordpress``` in the left-hand menu. Now, choose a domain where you want to install Wordpress to. You can also specify a sub-directory (eg. yourdomain.tld/my-wordpress). If you do not want to install Wordpress into sub-directory, leave the ```Sub-directory``` field empty. Enter your admin username, your admin e-mail address (e-mail must be existing and working - to this address you will receive admin credentials to Wordpress admin panel) and choose a Wordpress language. Now just click on the ```Save``` button.

![Wordpress 1-Click Installer](img/oneclick_wordpress.png)

!!! note
	We recommend to install wordpress to empty folder. The existing data will be automatically backed-up.

!!! note
	Installation can take a few minutes - usually it's about two minutes. Login credentials to your Wordpress admin will be sent to e-mail address you entered.

## Delete Wordpress installation from 1-Click Installer

If you want to remove previous Wordpress installation made by 1-Click Installer, just click on the red bin button in the list of installed 1-Click apps. All data (FTP, MySQL) will be permanently deleted.

## WP-CLI: How to use wp-cli to manage Wordpress from cli

WP-CLI is a terminal interface through which you can work with WordPress directly via the terminal and SSH connection. You can, for example, download installation files, install plugin, and perform advanced edits over multiple sites at once.

Using WP-CLI you can manage your whole Wordpress website from shell console, with super-admin privileges. It saves your time and allows you to automatise some processes or help managing a bigger Wordpress websites and installations.

WP-CLI support is available on our VIP hosting. All you need is active SSH access.

## WP-CLI Usage Examples

### Install files download (Wordpress package download)

```
$ cd /web
$ wp core download --path=dev/wp-cli
Creating directory '/home/sourcecode.sk/sub/dev/wp-cli/'.
Downloading WordPress 4.9.8 (en_US)...
Using cached file '/home/.wp-cli/cache/core/wordpress-4.9.8-en_US.tar.gz'...
Success: WordPress downloaded.
```

With the "wp core download" command, you download the installation files to the folder you are currently in. In the example above, we've set --path=dev/wp-cli to set the files to the dev/wp-cli folder in main web folder.

### Creating a new wp-config.php file

!!! hint
	Before you start creating a wp-config file, [create a new MySQL Database](mysql_databases/) with a new database user first.

```
$ cd /web/dev/wp-cli
$ wp config create --dbname=wpclidemo --dbuser=wpclidemuser --dbpass=password --dbhost=mysql5-1
Success: Generated 'wp-config.php' file.
```

Entering the "wp config create" command you create a new wp-config.php file with your database data settings. At this point, it is worth mentioning that the "wp db create" command will no longer work because of the nature of our web / DB servers - you can not create a new database using WP-CLI. However, you can work in the local environment.

!!! note
	Creation of MySQL database and database user is available only in [Hosting Control Panel](https://my.nuclear.hosting).

### Installing Wordpress with database migration

When you have downloaded Wordpress files, created a configuration file (wp-config.php), you can run Wordpress installation process.

In the directory where you have downloaded Wordpress and created wp-config.php file, just run (do not forget to adjust CAPS variables by your needs):

```
$ wp core install --url="ENTER_URL" --title="ENTER_WEBSITE_TITLE" --admin_user="ENTER_ADMIN_USERNAME" --admin_email="ENTER_ADMIN_EMAIL"
```

!!! hint
	When process is completed, do not forget to copy auto-generated admin password.

### Plugins update

With the "wp plugin update --all" command, you will instantly update all installed WordPress plugins in that folder. In the example below, you can also see the form of the output. You surely noticed that no WordPress password was needed - if you are connected via SSH, with WP-CLI you have full control over everything.

The command above update all you plugins, but you can update them selectively:

```
$ wp plugin update PLUGIN_NAME
```

Where PLUGIN_NAME is name of the plugin you want to update.

### Themes update

To update all your installed themes just enter in the Wordpress directory:

```
$ wp theme update --all
```

You can also update themes selectively:

```
$ wp theme update THEME_NAME
```

Where THEME_NAME is name of the theme you want to update.

### Wordpress update

Updating Wordpress installation is also very easy. You can update whole Wordpress installation by command. In the Wordpress directory run:

```
$ wp core update
```

### More useful WP-CLI commands

To list of all WP-CLI useful features please visit WP-CLI Guide (link bellow), or you can use WP-CLI Help by entering:

```
$ wp help
```

We consider these functions to be very useful:

 * wp comment - Creates, updates, deletes, and moderates comments.
 * wp core - Downloads, installs, updates, and manages a WordPress installation.
 * wp cron - Tests, runs, and deletes WP-Cron events; manages WP-Cron schedules.
 * wp export - Exports WordPress content to a WXR file.
 * wp import - Imports content from a given WXR file.
 * wp media - Imports files as attachments, regenerates thumbnails, or lists registered image sizes.
 * wp option - Retrieves and sets site options, including plugin and WordPress settings.
 * wp plugin - Manages plugins, including installs, activations, and updates
 * wp post - Manages posts, content, and meta.
 * wp role - Manages user roles, including creating new roles and resetting to defaults.
 * wp site - Creates, deletes, empties, moderates, and lists one or more sites on a multisite installation.
 * wp super-admin - Lists, adds, or removes super admin users on a multisite installation.
 * wp theme - Manages themes, including installs, activations, and updates.
 * wp user - Manages users, along with their roles, capabilities, and meta.

## More WP-CLI options

A [WP-CLI guide](https://make.wordpress.org/cli/handbook/) is available on wordpress.org, look for [recommendations](https://make.wordpress.org/cli/handbook/quick-start/) or a [list of all commands](https://developer.wordpress.org/cli/commands/).