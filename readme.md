# codeigniter-composer-boilerplate

> A boilerplate for getting started with latest [CodeIgniter](https://github.com/bcit-ci/CodeIgniter) using [Composer](https://github.com/composer/composer).

## Getting started

Only follow these three steps:

1) Install [Composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).

2) Clone or download the [CodeIgniter](https://github.com/bcit-ci/CodeIgniter) source code.

3) Edit the `./index.php` root file and add the composer autoloader:

```php
// Composer autoload (add this line before CodeIgniter core)
require_once __DIR__ . '/vendor/autoload.php';

require_once BASEPATH.'core/CodeIgniter.php';

```

4) Create a `composer.json` file in the root. This file is for your third-party packages that you want to use.

```json
{
  "description": "My first application",
  "require": {
    "php": ">=5.5"
  }
}
```

## Testing the configuration

1) For example, install [GImage](https://github.com/joseluisq/gimage) package:

```sh
composer require joseluisq/gimage
```

2) In your `application/controllers/Welcome.php` add these lines:

```php
<?php

defined('BASEPATH') OR exit('No direct script access allowed');

use GImage\Image;

class Welcome extends CI_Controller {

	public function index()
	{

		// This code will output a Github image in your browser.
		$url = 'https://assets-cdn.github.com/images/modules/logos_page/Octocat.png';

		$avatar = new Image();
		$avatar->load($url)->output();
	}

}
```

3) Run your server and navigate.
