+++
date = "2017-04-10T16:42:12+01:00"
draft = false
weight = 10
description = "Popular and adjustable menu and navigation option"
title = "Setup Commander"
bref= "Installing Commander"
toc = true
+++

### How to install Commander

Commander is a simple tool designed to be light so that it is quick and easy to deploy. It’s main purpose is to send emails from the message queue. It’s commonly deployed to an EC2 instance and run from there to take full advantage of AWS free tier.

#### Installing Commander on EC2

CME provides a nice CLI tool that installs a copy of commander on EC2. For this to work you need to have AWS setup. Edit your CME .env file and add your AWS details then run the following command from a terminal and follow on screen instructions

```sh
php artisan cme:install-commander -i1
```

#### Installing Commander on your server

You will want to do this if you are using Amazon as an smtp provider and sending emails through SES. To avoid charges and take advantage of the **60K free emails** per month that amazon offers on its free tier.

Commander comes with a install script (install.sh), which installs all the dependencies. At this point this script only works on debian systems

**Debian**

- Download and extract commander from here
- Run install.sh to setup commander

**Non-Debian**

- Download and extract commander from here
- Install dependencies
  - Monit
  - Curl
  - PHP Curl
  - PHP Cli
  - PHP MySQL
  - Composer
- Run composer install
- Setup monit - Use template provided within Commander (monit-template)
