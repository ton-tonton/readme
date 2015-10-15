# Remove /public from url laravel 4.2
1. Add ``DocumentRoot "path/to/laravel 4.2 project/public"`` in virtual host

2. Remove __public__ folder
  * create ``local`` folder
  * move all file except ``public/`` to ``local/``
  * move all file in ``public/`` to ``root project`` and remove empty ``public/``
  * file stucture look like this
  
  ```
  laravel root
  -- local
    | -- CONTRIBUTTING.md
    | -- app
    | -- artisan
    | -- bootstrap
    | -- composer.json
    | -- composer.lock
    | -- phpunit.xml
    | -- server.php
    | -- vendor
    | -- .gitattributes
    | -- .gitignore
  -- packages
  -- favicon.ico
  -- index.php
  -- readme.md
  -- robot.txt
  -- .htaccess
  ```
  
  * ``local/bootstrap/paths.php`` 
  
    * change **``'public' => __DIR__.'/../public',``** to
    * **``'public' => __DIR__.'/../../',``**
    
  * ``index.php``
  
    * change **``require __DIR__.'/../bootstrap/autoload.php';``** to
    * **``require __DIR__.'/local/bootstrap/autoload.php';``**
    * change **``$app = require_once __DIR__.'/../bootstrap/start.php';``** to
    * **``$app = require_once __DIR__.'/local/bootstrap/start.php';``**
