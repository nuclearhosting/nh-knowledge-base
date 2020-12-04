# Shell & SSH Access

For our VIP Membership we provide access via SSH to the limited Shell enviroment. This function is dedicated especially for more advanced users whos are familiar with CLI and Linux enviroment. The goal of this service is not to offer a full-fledged root shell, but to simplify or enable some more complicated operations directly on the server.

The shell works separately for each system user. New Shell user can be created in the [Hosting Control Panel](https://my.nuclear.hosting).

!!! note
	Shell (incl. SFTP access) is available only for VIP Membership.

It is also possible to use SSH keys and it is not always necessary to enter a password when connecting. Bash running in normal mode is used as a shell, so it is possible to redirect input and output from / to a file or to pass data between commands using a pipe.

## Available Shell commands

### Standard Shell commands

```
cp	egrep	false	grep	gzip	less	ls		more	nano	rm		sed		touch	uncompress
cat	date	echo	fgrep	gunzip	chmod	mkdir	mv		pwd		rmdir	tar		zcat	mysqldump
awk	cut		find	head	less	mcedit	md5sum	scp		ssh		tail	wget	clear	vim.tiny
mc	mcview	mysql	rsync	sort	tac		tr		vi		wc		zip		unzip	gawk	basename
id	diff	patch	host	du		bzip2	bunzip2	xz		unxz	bzcat	xzcat	realpath
```

EmShell commands can be executed only as: ```bash yourscript.sh```.

### Special Shell commands

**composer**

Syntax: ```composer [args]```

!!! note
	You cannot run composer self-update. If you need to use another version of the Composer, you can download it on your own from Composer official website.

**ffmpeg**

Syntax: ```ffmpeg [args] input file output file```

!!! note
	The output file is always the last parameter in the command.

**ffprobe**

Syntax: ```ffprobe [args] input file output file```

!!! note
	The output file is always the last parameter in the command.

**phpXY**

Syntax: ```phpXY script [--] [parameters]```

Runs a PHP script "script" with an optional parameter or parameters "parameters", any output is written to standard output. Optional delimiter ```--``` should be used in a situation where a parameter starting with a hyphen is passed to the PHP script.

Where XY is PHP version you want to execute your script by. Supported PHP versions are:

  - PHP5.6 - php56
  - PHP7.0 - php70
  - PHP7.1 - php71
  - PHP7.2 - php72
  - PHP7.3 - php73
  - PHP7.4 - php74

Examples:

```
php73 myscript.php
php70 myscript.php -- --param=value
php56 myscript.php -- some:param
```

**php**

Syntax: ```php script [--] [parameters]```

Same as previous command ```phpXY``` but it uses default PHP version configured in your shell. The default PHP version is same as PHP version you are using on your website. So, if you have configured PHP7.3 for your website in the Hosting Control Panel, php7.3 will be used as default for ```php``` command in your shell. The command usage (syntax) is the same as in examples above.

To change default PHP version for ```php``` command use ```php_chooser``` command first. This is described bellow.

**wp**

Syntax: ```wp command [global params]```

Command ```wp``` is a WP-CLI utility to manage your Wordpress via CLI. More informatio about WP-CLI you can find in [this article](/wordpress/#wp-cli-how-to-use-wp-cli-to-manage-wordpress-from-cli) or the official WP-CLI utility [website](https://wp-cli.org).

**wkhtmltoimage**

Syntax: ```wkhtmltoimage [global options] input output```

Command is used to convert HTML page to image. As ```input``` use static HTML page from a file or you can use remote website by http protocol. As output file is an image.

**wkhtmltopdf**

Syntax: ```wkhtmltopdf [global options] input output```

Command is used to convert HTML page to a PDF document. As ```input``` use static HTML page from a file or you can use remote website by http protocol. As output file is an PDF document.

**php_chooser**

Syntax: ```php_chooser version```

Command is used to change default PHP version for ```php``` command. Parameter ```version``` is required and valid values are:

  - php5.6
  - php7.0
  - php7.1
  - php7.2
  - php7.3
  - php7.4

Example: To change default PHP version to PHP7.2 use: ```php_chooser php7.2```

!!! information
	Changes take effect immediately.

## Bash script example

🚧 TODO