# CodeIgniter Simple and Secure Twig

[![Latest Stable Version](https://poser.pugx.org/kenjis/codeigniter-ss-twig/v/stable)](https://packagist.org/packages/kenjis/codeigniter-ss-twig) [![Total Downloads](https://poser.pugx.org/kenjis/codeigniter-ss-twig/downloads)](https://packagist.org/packages/kenjis/codeigniter-ss-twig) [![Latest Unstable Version](https://poser.pugx.org/kenjis/codeigniter-ss-twig/v/unstable)](https://packagist.org/packages/kenjis/codeigniter-ss-twig) [![License](https://poser.pugx.org/kenjis/codeigniter-ss-twig/license)](https://packagist.org/packages/kenjis/codeigniter-ss-twig)

This package provides simple Twig integration for [CodeIgniter](https://github.com/bcit-ci/CodeIgniter) 3.0.

## Folder Structure

```
codeigniter/
└── application/
    └── libraries/
        └── Twig.php
```

## Requirements

* PHP 5.4.0 or later

## Installation

### With Composer

~~~
$ cd /path/to/codeigniter/
$ composer require kenjis/codeigniter-ss-twig:1.0.x@dev
~~~

Install `libraries/Twig.php` to your CodeIgniter application folder:

~~~
$ php vendor/kenjis/codeigniter-ss-twig/install.php
~~~

* Above command always overwrites exisiting files.
* You must run it at CodeIgniter project root folder.

### Without Composer

Download the latest Twig v1.x: https://github.com/twigphp/Twig/releases

Unzip and install to `application/third_party` folder.

Download the latest codeigniter-ss-twig.

Unzip and copy `codeigniter-ss-twig/libraries/Twig.php` to `application/libraries` folder.

Remove comment marks below and fix the path for `Autoloader.php`:

~~~diff
--- a/libraries/Twig.php
+++ b/libraries/Twig.php
@@ -9,10 +9,8 @@
  */
 
 // If you don't use Composer, uncomment below
-/*
 require_once APPPATH . 'third_party/Twig-1.xx.x/lib/Twig/Autoloader.php';
 Twig_Autoloader::register();
-*/
 
 class Twig
 {
~~~

## Usage

Load Twig library:

~~~php
$this->load->library('Twig');
~~~

Render Twig template and output to browser:

~~~php
$this->twig->display('welcome', $data);
~~~

Above code renders `views/welcome.twig`.

> **Note:** I've changed the method name from `render()` to `display()`. Now `render()` method returns string only.

Render Twig template:

~~~php
$output = $this->twig->render('welcome', $data);
~~~

Above code renders `views/welcome.twig`.

### Supported CodeIgniter Helpers

* `base_url`
* `site_url`
* `form_open`
* `form_close`
* `form_error`
* `set_value`
* `form_hidden`
* `anchor`

Some helpers are added the functionality of auto-escaping for security.

### Reference

* http://twig.sensiolabs.org/documentation

## How to Run Tests

~~~
$ cd codeigniter-ss-twig
$ composer install
$ phpunit
~~~

## Other Implementations for CodeIgniter 3.0

* https://gitlab.com/david-sosa-valdes/ci-attire

## Related Projects for CodeIgniter 3.0

* [CodeIgniter Composer Installer](https://github.com/kenjis/codeigniter-composer-installer)
* [Cli for CodeIgniter 3.0](https://github.com/kenjis/codeigniter-cli)
* [CI PHPUnit Test](https://github.com/kenjis/ci-phpunit-test)
* [CodeIgniter Doctrine](https://github.com/kenjis/codeigniter-doctrine)
* [CodeIgniter Deployer](https://github.com/kenjis/codeigniter-deployer)
* [CodeIgniter3 Filename Checker](https://github.com/kenjis/codeigniter3-filename-checker)
