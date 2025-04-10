```
curl -s "https://laravel.build/example-app" | bash

sail composer require inertiajs/inertia-laravel

docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php83-composer:latest \
    composer install --ignore-platform-reqs

sail up
sail composer run dev
```
