# Via Docker

## Installation

installing Openclassify on windows docker desktop

### 1. Docker Desktop on Windows

Download docker desktop ([Download](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe))

install docker desktop according to [Install Docker Desktop on Windows](https://docs.docker.com/desktop/windows/install/)

when you installed the docker desktop successfully. restart windows

### 2. Install WSL2 on Windows

You need to download [WSL2 Linux kernel update package for x64 machines](https://wslstorestorage.blob.core.windows.net/wslblob/wsl\_update\_x64.msi)

follow steps 4 and 5 of this [Docs](https://docs.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)

after you installed and updated WSL2 Linux kernel successfully. restart the docker desktop.

it should run without error.

### 3. Install ubuntu 20.04 LTS on Windows

open Mircosoft Store on your Windows

in the Windows Store search for `Ubuntu 20.04.4 LTS`

![image](https://user-images.githubusercontent.com/100101497/172398329-c377a444-ae54-4cbe-bbe2-61d87349893d.png)

Download Ubuntu 20.04.4 LTS and install it on the windows store

open it

It will start installing ubuntu on your windows and ask for a username and password, so set a username and password.

### 4. Docker Desktop, WSL2, and ubuntu configuration

open the docker desktop and go to `Settings` then go to `General` tab and set options the same as below:

![image](https://user-images.githubusercontent.com/100101497/172401622-9907311a-dbc6-4dcb-8a0d-dc8ba3a4fb8b.png)

go to `Resources` and `WSL INTEGRATION` tab and set options like the below:

![image](https://user-images.githubusercontent.com/100101497/172402503-baf9befb-e547-452d-9894-fc9884d0bbd5.png)

Click on `Apply & restart` button

### 5. Set WSL as Phpstorm terminal

Open Phpstorm and go to File > Settings...

![image](https://user-images.githubusercontent.com/100101497/172404195-c9185467-3500-4128-aa4e-6013be8c9f6a.png)

then go to tools > terminal

in the application settings open the selectbox and select `wsl.exe --distribution Ubuntu-20.04` like below:

![image](https://user-images.githubusercontent.com/100101497/172405113-9549800e-61d7-4299-9dd4-40d94e369a82.png)

Click OK.

### 6. Install php7.4 on the WSL Ubunutu-20.04

open Ubunutu-20.04 on Windows

`sudo apt update -y && sudo apt-get update -y`

`sudo apt-get install php libapache2-mod-php php-dev php-zip php-curl php-pear php-mbstring php-mysql php-gd php-xml curl -y`

`PHP -v` you should see something like this:

![image](https://user-images.githubusercontent.com/100101497/172407097-64c25128-32d2-4eb6-9fe0-57a84cf33692.png)

try `composer --version` if it does not install so install it from [HERE](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-20-04)

### 7. Install Openclassify

open ubuntu

&#x20;`cd ~`

`git clone https://github.com/openclassify/openclassify.git`

`cd openclassify`

`git config core.fileMode false`

`composer install`

`composer require laravel/sail --dev`

`config/app.php` in `providers` add this line:

`\Laravel\Sail\SailServiceProvider::class,`

`mv .env-sail .env`

`alias sail="./bin/sail"`

`sail build --no-cache`

`sail up -d`

`sail artisan install --ready`

{% hint style="success" %}
Openclassify installed
{% endhint %}

#### admin panel:

{% hint style="success" %}
[http://localhost/admin](http://localhost/admin)

username: admin@example.com

password: admin
{% endhint %}

#### phpmyadmin:

{% hint style="success" %}
[http://localhost:88888](http://localhost:8888)

username: root
{% endhint %}



you can change this username and password in the .env file before running `sail up -d` command

{% hint style="warning" %}
#### All PHP artisan commands must run like `sail artisan <artisan command>`
{% endhint %}

{% hint style="warning" %}
#### Execute composer with sail: `sail composer <command>`
{% endhint %}

{% hint style="danger" %}
_**DON'T RUN COMMANDS WITHOUT SAIL**_
{% endhint %}

Access to project on Windows

in File Explorer on Windows

`\\wsl$\Ubuntu-20.04\home\{USER}\openclassify`

replace {USER} with your WSL ubuntu-20.04 username

also, you can open from this address in the Phpstorm or any IDE

\
