start-app
=========

[![Build Status](https://travis-ci.org/Metabor/start-app.svg?branch=master)](https://travis-ci.org/Metabor/start-app)

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/59f779ee-0d52-4b95-9f0b-eb48d86676d2/big.png)](https://insight.sensiolabs.com/projects/59f779ee-0d52-4b95-9f0b-eb48d86676d2)

Symfony 2 Boilerplate For Building Web Applications (based on symfony-standard with integrated bundles)
It is intended to kickstart your development, serving as an alternative to [symfony-standard edition](https://github.com/symfony/symfony-standard/tree/master/web)

Packagist link:
    https://packagist.org/packages/metabor/start-app

What it is made of
------------------

start-app depends on the following projects:


Installation in a Vagrant box (recommended)
-------------------------------------------

This feature comes from https://github.com/seiffert/symfony-vagrant
Thanks seiffert, i just included the vagrant folder from there and added a few puppet modules
This installs a complete linux setup including nodejs less java css

- Install vagrant on your system
  see [vagrantup.com](http://vagrantup.com/v1/docs/getting-started/index.html)
  
- Get a base box with puppet support
  see [http://www.vagrantbox.es/ list](http://www.vagrantbox.es/)
  e.g. http://puppet-vagrant-boxes.puppetlabs.com/ubuntu-server-1204-x64.box
  add it to your system: vagrant box add ubuntu-server-1204 http://puppet-vagrant-boxes.puppetlabs.com/ubuntu-server-1204-x64.box

- Install composer on your system
  see [getcomposer.org](http://getcomposer.org/doc/00-intro.md)

```
# clone the symfony-bootstrap edition:
git clone https://github.com/phiamo/symfony-bootstrap.git
# enter directory
cd symfony-bootstrap
# init submodules
git submodule init
# update submodules
git submodule update
# copy default parameters to local parameters
cp app/config/parameters.yml.default app/config/parameters.yml
# tell composer to install including dev (BootstrapSandboxBundle)
composer.phar install --dev
# enter vagrant dir
cd vagrant
# copy Personalization.dist to Personalization
cp Personalization.dist Personalization
# modify to your needs
# take the vm up
vagrant up
# wait until everything is setup, might take some mins on my quite fast system with ssd takes around 5 mins (downloading java, nodejs, etc)
# go to your browser
# http://192.168.10.42/app_dev.php
```

Installation on a Host System
-----------------------------

Before installing symfony-bootstrap, the following needs to be installed beforehand:

- [composer](http://getcomposer.org)
- [node.js](http://nodejs.org)
- [Less installation](https://github.com/phiamo/MopaBootstrapBundle/blob/master/Resources/doc/less-installation.md) (Mac users please note the known issues at the bottom of the Less installation instructions)

To install start-app, do the following:

```
git clone git://github.com/phiamo/symfony-bootstrap.git
cd symfony-bootstrap
cp app/config/parameters.yml.dist app/config/parameters.yml
curl -s https://getcomposer.org/installer | php
php composer.phar install --dev
app/console assetic:dump
```


It should now work. If you run into any issues, feel free to open a new issue or make a new pull request.


What's inside?
---------------

It is configured with the following defaults:

  * Twig is the only configured template engine;

  * Doctrine ORM/DBAL is configured;

  * Swiftmailer is configured;

  * Annotations for everything are enabled.
  
  * bootstrap(http://github.com/twitter/bootstrap) - Twitter's Bootstrap

It comes pre-configured with the following bundles:

  * **FrameworkBundle** - The core Symfony framework bundle

  * **SensioFrameworkExtraBundle** - Adds several enhancements, including
    template and routing annotation capability

  * **DoctrineBundle** - Adds support for the Doctrine ORM

  * [**TwigBundle**] - Adds support for the Twig templating engine

  * [**SecurityBundle**] - Adds security by integrating Symfony's security
    component

  * [**SwiftmailerBundle**] - Adds support for Swiftmailer, a library for
    sending emails

  * [**MonologBundle**] - Adds support for Monolog, a logging library

  * [**AsseticBundle**] - Adds support for Assetic, an asset processing
    library

  * **WebProfilerBundle** (in dev/test env) - Adds profiling functionality and
    the web debug toolbar

  * **SensioDistributionBundle** (in dev/test env) - Adds functionality for
    configuring and working with Symfony distributions

  * [**SensioGeneratorBundle**] (in dev/test env) - Adds code generation
    capabilities

  * **AcmeDemoBundle** (in dev/test env) - A demo bundle with some example
    code
    
  * [MopaBootstrapBundle](http://github.com/phiamo/MopaBootstrapBundle) - Easy integration of twitters bootstrap into symfony2

  * [MopaBootstrapSandboxBundle](http://github.com/phiamo/MopaBootstrapSandboxBundle) - Seperate live docs from code
  
