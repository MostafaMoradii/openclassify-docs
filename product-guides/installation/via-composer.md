# Via Composer



{% hint style="warning" %}
Do not create <mark style="color:red;">`.env`</mark> file just yet - Installer will generate one for you.
{% endhint %}

```
composer create-project openclassify/openclassify
```

#### Running the Installation Wizard

After downloading its dependencies with:

```
composer install
```

you will need to install the software in order to get started. By this time you should be able to visit your site's URL which will redirect you to the installer: `http://yoursite.com/installer`

#### Using the CLI Installer

```
php artisan install
```

You will be prompted for details in order to proceed with the installation process.

> You may need to run `ulimit -n 1024` before installing via CLI to temporarily increase your max open files limit.

**Automating the CLI Installer**

You can automate the installer by creating your own .env file with something like this:

```
APP_ENV=local
APP_DEBUG=true
APP_KEY=zfesbnTkXvooWVcsKMw2r4SmPVNGbFoS
DB_CONNECTION=mysql
DB_HOST=localhost
DB_DATABASE=workbench
DB_USERNAME=root
DB_PASSWORD=root
APPLICATION_NAME=Default
APPLICATION_REFERENCE=default
APPLICATION_DOMAIN=localhost
ADMIN_EMAIL=info@openclassify.com
ADMIN_USERNAME=admin
ADMIN_PASSWORD=password
LOCALE=en
TIMEZONE=Turkey/Istanbul
```

> The APP\_KEY must be exactly 32 characters in length.

Then run the installer and indicate that the system is ready to install:

```
php artisan install --ready
```
