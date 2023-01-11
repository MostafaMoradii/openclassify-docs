# Asset Management

Clears all assets and generated image cache.

\
The optional `path` argument specifies the path relative to your application's public asset path. In this way, you can easily clear `public` or `admin` theme cache directories.

```
php artisan asset:clear         // Clear everything
php artisan asset:clear public  // Clear public theme cache
```
