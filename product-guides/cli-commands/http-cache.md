# HTTP Cache

#### httpcache:clear

Clears all HTTP cache.

```
php artisan httpcache:clear
```

#### httpcache:warm

Warms HTTP cache by crawling your sitemap.

The `--sleep` option specifies how long in `seconds` to wait between each request. HTTP cache will be warmed as fast as possible by default.

The `--clear` flag will call `httpcache:clear` prior to warming.

```
php artisan httpcache:warm --sleep=5 --clear
```
