+++
date = "2017-04-10T16:42:12+01:00"
draft = false
weight = 10
description = "Popular and adjustable menu and navigation option"
title = "Setup CME"
bref= "Installing CME is easy and can be done in 4 steps."
toc = true
+++

### Download & Extract

The first step to installing CME is to download the latest CME version from the links below. Extract and upload to your web server using your favourite S/FTP client

You can download CME from github here: [Download CME]({{page.gitBase}})

You can install CME on a subdomain of your website. e.g cme.yourdomain.com, so that going to **cme.yourdomain.com** points to your instance of CME.

### Configure Web Server

The next step after you have extracted CME onto your server is to configure it's Virtual Host (vHost) so that you can run it from a web browser

> If you are using Apache web server, please ensure that you have <strong>mod_rewrite</strong> enabled. For details on how to do this, see [here](http://stackoverflow.com/a/5758551/742167)

If you are on a shared host, simply create a subdomain and point it to the directory where you have extracted CME.

For VPS users or users on a dedicated server, you will need to add the config below into your vhosts file

#### Vhost Setup

Copy the following Vhost directive into your vhost conf file.

```bash
<VirtualHost *:80>
   DocumentRoot "path/to/cme/public"
   ServerName cme.domain.com
   <Directory "path/to/cme/public">
   AllowOverride All
   </Directory>
   ErrorLog "logs/cme.error.log"
   CustomLog "logs/cme.access.log"
   common
</VirtualHost>
```

### Run CME Web Installer

After you are done with the above configurations. Point your browser to the domain where you have setup CME and follow the installation wizard to complete installation. This should install the database and create a temp user for you to login

CME installer is self explanatory and you should be fine just following the instruction on the screen.

> If you get an error saying page /login not found, this is probably because mod rewrite is not enabled and AllowOverride directive has not been specified in the vhost.

#### Requirements

CME installer will perform a check against your server to make sure
it meets all the requirements to run CME. The installer will not run
until all requirements are met. CME requires the following:

- PHP 5.4 or greater
- MySQL or mariadb server
- PHP modules
  - php mcrypt
  - php mbstring
  - php curl
- A web server like apache
- SMTP Provider - e.g SES - with an AWS account you can get to send over
  700k emails in 12 months under your free-tier

### Setup up Background Processes

Behind the scenes, CME needs to run some background processes to
keep everything running smoothly. For example, there is a background
process that handles importing subscribers from CSV files or API. This runs
in the background so you can carry on with creating lovely campaigns
while CME works hard to import the lists as fast as possible.

These background processes can be set up as either **cron jobs** or **monit
processes**.

At the end of the installation process, CME will generate crontab and
monit configuration for you based on your installation settings. Copy
the config that is relevant to your setup and apply it to your
server

If you are running CME on a VPS or dedicated server and
have monit installed, copy the monit-template file and make the paths to
match your CME installation. To learn more about monit go here:
<a href="https://mmonit.com/monit/">https://mmonit.com/monit/</a>

If you don’t have monit or don't wish to install it then you need to copy
the crontab config to your crontab file
