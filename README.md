# Novactive eZ Static Templates bundle

----

This repository is what we call a "subtree split": a read-only copy of one directory of the main repository. 
It is used by Composer to allow developers to depend on specific bundles.

If you want to report or contribute, you should instead open your issue on the main repository: https://github.com/Novactive/Nova-eZPlatform-Bundles

Documentation is available in this repository via `.md` files but also packaged here: https://novactive.github.io/Nova-eZPlatform-Bundles/master/StaticTemplatesBundle/README.md.html

----

[![Downloads](https://img.shields.io/packagist/dt/novactive/ezstatictemplatesbundle.svg?style=flat-square)](https://packagist.org/packages/novactive/ezstatictemplatesbundle)
[![Latest version](https://img.shields.io/github/release/Novactive/NovaeZStaticTemplatesBundle.svg?style=flat-square)](https://github.com/Novactive/NovaeZStaticTemplatesBundle/releases)
[![License](https://img.shields.io/packagist/l/novactive/ezseobundle.svg?style=flat-square)](LICENSE)

Novactive eZ Static Templates bundle is an eZ Platform bundle providing a way to access twig templates from an url.

It uses the [siteaccess](https://doc.ezplatform.com/en/latest/guide/siteaccess/) and the [design engine](https://doc.ezplatform.com/en/latest/guide/design_engine/) provided by eZ Platform.

## Features

When you access a siteaccess in the siteaccess group `static_group`, it will take the url and show the twig template having the corresponding path.

You can configure as many siteaccess as you want, and using the design engine you can configure a different theme for each siteaccess.

As we are using the siteaccess feature, u can also use the [permissions](https://doc.ezplatform.com/en/latest/guide/permissions/) to control the access.

### Example

Considering a theme `static_test`, a siteaccess `static-test` is automatically generated. The siteaccess is then matched by URI, the url `http://localhost/static-test/news/details` will show the template in `Resources\views\themes\static_test\news\details.html.twig`

## Installation

### Get the bundle

Run `composer require novactive/ezstatictemplatesbundle` to install the bundle and its dependencies.

### Register the bundle

Activate the bundle in `app\AppKernel.php` file.

```php
// app\AppKernel.php

public function registerBundles()
{
   ...
   $bundles = array(
       new FrameworkBundle(),
       ...
       new Novactive\Bundle\EzStaticTemplatesBundle\EzStaticTemplatesBundle(),
   );
   ...
}
```

### Configuration

The siteaccess configuration is autogenerated based on existing themes whose name start with "static_"
