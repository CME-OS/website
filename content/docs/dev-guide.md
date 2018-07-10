+++
title = "Dev Guide"
description = "Here you will find all technical information you need to work on CME."
date = 2018-07-10T20:09:59+01:00
weight = 100
draft = false
bref = "Welcome to CME developer's guide, here you will find all technical information you need to work on CME"
toc = true
+++

### Projects

CME is made up of a number sub-systems that come together to provide users with its full capability and as a developer you can choose to contribute to any of these systems discussed below:

#### CME Website

This is the website of CME that provides information about the CME the product. It is where this documentation is hosted. Here you can contribute as an author, designer. Most of the website is hosted on github and powered by Jekyll.

[View on GitHub](https://github.com/CME-OS/cme-os.github.io)

#### CME Web App

The web app is the main system - built with laravel v4.2. It serves as the backend for creating and managing campaigns. Check out the demo to have an idea of what it is.

[View on GitHub](https://github.com/CME-OS/cme)

#### CME API

With third party integration in mind, CME also has an API which allows others to communicate with any CME instance and perform common tasks on it. The API is built with the Slim framework

More technical information can be found here

[View on GitHub](https://github.com/CME-OS/cme-api)

#### CME Kernel

This is the heart of the project. It provides all the core functionality of CME and encapsulates all the juicy business logic.

[View on GitHub](https://github.com/CME-OS/cme-kernel)

#### CME Data

This is a repository of all of CME data types. To enforce certain data structure across the project, we use this set of objects

[View on GitHub](https://github.com/CME-OS/cme-data)

#### CME SDK

The SDK is currently only available in PHP but we welcome more development in other languages. The SDK allows for third party integration. Basically it’s a wrapper around the API that exposes a set of methods that make it easier to work with the API.

[View on GitHub](https://github.com/CME-OS/cme-sdk)

#### Commander

Commander is a simple tool designed to be light so that it is quick and easy to deploy. It’s main purpose is to send emails from the message queue. It’s commonly deployed to an EC2 instance and run from there to take full advantage of AWS free tier.

NOTE: Commander requires access to your CME database.

[View on GitHub](https://github.com/CME-OS/cme-commander)
