# lumen-contentful

[![Build Status](https://travis-ci.org/digiaonline/lumen-contentful.svg?branch=master)](https://travis-ci.org/digiaonline/lumen-contentful)

This is a basic Lumen service provider for the Contentful PHP SDK.
 
## Requirements

* PHP >= 7.0
* Lumen 5.x

## Installation

Install the library:

```bash
composer require nordsoftware/lumen-contentful
```

Register the service provider:

```php
$app->register(Nord\Lumen\Contentful\ContentfulServiceProvider::class);
```

Finally, copy `config/contentful.php` to your application's `config/` directory, then define the environment variables 
in your `.env` file

## Usage

Inject `Nord\Lumen\Contentful\ContentfulServiceContract` into your classes, then you'll be able to access the 
Contentful client by using the `getClient()` method:

```php
<?php

use Nord\Lumen\Contentful\ContentfulServiceContract;

class TestService
{

    public function __construct(ContentfulServiceContract $contentfulService)
    {
        $client = $contentfulService->getClient();
    }
}
``` 
