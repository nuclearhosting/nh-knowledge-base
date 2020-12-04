# CRON

Cron is a time-based jobs scheduler, which schedules a command or script on your server to run automatically at a specified time and date. A cron job is the scheduled task itself. Cron jobs can be very useful to automate repetitive tasks.

Scripts executed as a cron job are typically used to modify files or databases. However, they can perform other tasks that do not modify data on the server, like sending out email notifications. Cron jobs can be also configured to trigger specified URL via HTTP/HTTPS protocol.

There is a limit in the minimum execution time period for crons. For Basic members, there is a limit 15min minutes period and for VIP members is 5 minute period. For shared web hosting is not possible to configure cron for every minute or lower than 5-minute interval. A maximum number of cron tasks is limited to 5 for Basic membership and an unlimited number for VIP membership.

Cron jobs time annotation is like: execute a script called myscript.sh on every 15 minutes every hour, every day of the month, every month and every day of the week or execute a script called myscript.sh on 7th minute, 7 am, every day of the month, from January to April and every Friday only.

We are support two kind of cron jobs:
  - Webcron - available for both Basic and VIP memberships
  - CLI Cron - available only for VIP memberships

## Webcron

Webcron will call defined URL via HTTP/HTTPS protocol. You can define specific URL which will be executed via HTTP GET request. The output can be saved to the logfile optionaly.

!!! note
	It is not possible to execute other than GET HTTP request via Webcron.

Please keep in mind that using webcrons may lead to some limitations. We do not recommend to configure webcrons to execute URLs which are slow responding or running too long because generating or processing a lot of data (for example imports, xml / json parsing, etc.). The reason is that on HTTP requests are applying standard webserver and PHP limits on the server-side which may leed to the premature end of script execution.

### How to configure Webcron

!!! important
	You can configure webcron only on an actual domain where webcron you are configuring. You cannot configure webcron for 3rd party domains, not hosted on your hosting account.

In your [Hosting Control Panel account](https://my.nuclear.hosting), navigate to ```Sites``` section and in the left-hand menu click on the ```Cron Jobs```. In the list of created Cron jobs click on the ```Add new Cron job``` button.

In the form fill the values:

 - **Parent website:** a domain you are configuring cron for
 - **Minutes:** in what minute or minutes do you want to execute your cron job. Allowed values are: */XX (every XX minutes) or X (at Xth minute). You can specify value from 0 to 59 range.
 - **Hours:** in what hour / hours do you want to execute your cron job. Allowed values are: * (every hour), */XX (every XX hours), X (at X), X-Y (every hour from X to Y). There is a 24hours format used.
 - **Days of month:** in what days of month do you want to execute your cron job. Allowed values are: * (every day), */XX (every XX days), X-Y (every day from Xth to Yth day of month). You can specify value from 1 to 31 range.
 - **Months:** in what months do you want to execute your cron jobs. Allowed values are: * (every month), X-Y (every month from X to Y), X (at Xth month). You can specify value from 1 to 12 range.
 - **Days of week:** in what days of the week do you want to execute your cron job. Allowed values are: * (every day of the week), X (at Xth day of the week), X-Y (every day from X to Y). You can specify value from 1 to 7 range, when 1 is Monday and 7 is Sunday.
 - **Command to run:** Enter your HTTP/HTTPS URL which you want to execute at the specified time. **Always use http:// or https:// as a prefix when you configuring Webcron**, otherwise it will be not configured properly. For example https://nuclearhosting.eu/web-hosting.
 - **Log output:** you can enable logging of the destination URL output. To the log is saved output which is returned by the executing URL. The cron log is located in ```./private/cron_wget.log```. Cron logfiles are rotated regularly.
 - **Active:** you can set this Cron job active or inactive. Inactive cron jobs are not executing.

!!! note
	You can configure only one specific time period. You cannot configure records like these ones: 1-3,6 or */7,*/9 etc. Only one single time period is allowed. If you need to configure such multiple time periods, create multiple cron jobs.

!!! tip
	If you need to specify HTTP Auth-based URL location, use syntax as follows: https://username:password@www.example.com/your_cron.php

When you are done, just click on the ```Save``` button.

![Cron Add](img/cron_create.png)

## CLI Cron

!!! note
	CLI Crons are available only for VIP memberships.

CLI Cron allows you to configure direct PHP or bash script execution, without necessity of webserver (HTTP/HTTPS). You can specify exactly what PHP script will be executed by using PHP-CLI. You can also specify execution of bash scripts ([available commands are limited](shell.md)) for more complex cron job tasks (deployments from Git repository, etc.).

The benefit of this method is that there are no standard webserver limits applied and many PHP limits are much higher in value than for webserver (php.ini for CLI is different than for webserver).

### How to configure CLI Cron

In your [Hosting Control Panel account](https://my.nuclear.hosting), navigate to ```Sites``` section and in the left-hand menu click on the ```Cron Jobs```. In the list of created Cron jobs click on the ```Add new Cron job``` button.

Steps are basically the same as when creating Webcron job (described in the section above). The only difference are:

 - **Command to run:** enter command you wish to execute. You can execute either PHP script or shell script. Please note that shell script has to have execution rights (chmod with +x option) and has to contains [allowed commands](shell.md). There is also necessary to enter command in the right format. Please read bellow the command syntax.
 - **Log output:** you can enable logging of the script output. To the log is saved output which is returned by the script. The cron log is located in ```./private/cron.log``` or ```./private/cron_error.log``` if error during execution has occured (STDERR is logged). Cron logfiles are rotated regularly.

#### Command syntax

**PHP scripts**

Example 1 (Laravel framework): You want to execute script named ```console``` located in the ```/web/app/bin``` directory with parameters ```app:import``` by PHP7.4. The ```Command``` will be as follow:

 ```cd [web_root]/app && php74 bin/console -- app:test```

!!! important
	Use [web_root] variable instead of trying to use full path. This variable will be converted to the right path inside your home directory regarding to chrooted shell enviroment.

!!! note
	Take note about ```--``` delimiter which is required if you are entering any parameters to PHP scripts. This delimeter spliting the parameters part. [Read more here](shell.md).

!!! info
	Supported PHP versions and its commands (in the example above is used php74 for PHP7.4 version) you can [find here](shell.md).

Example 2: You want to execute script ```mycron.php``` located in ```/web``` directory by PHP7.0. The ```Command``` will be as follow:

```cd [web_root] && php70 mycron.php```

!!! important
	Do not execute commands as follow - they will not works properly: ```php71 [web_root]/yourscript.php``` nor ```php71 [web_root]/app/bin/console```.

Example 3: You want to execute script ```deploy.sh``` located in ```/private``` directory which contains deploying steps of your application. The ```Command``` will be as follow:

```cd /private && bash deploy.sh```

!!! note
	Test your script via SSH before you configure it as a cron job. Set correct path's in your script, regarding to cron execution and directory you are testing from via SSH.

**More information about Shell and CLI scripts execution you can find on [this page](shell.md).**