OpenPhoto / Installation for Lighttpd
=======================
#### OpenPhoto, a photo service for the masses

## OS: Linux Ubuntu Server 10.04+

This guide instructs you on how to install OpenPhoto on an Ubuntu server.

----------------------------------------

### Prerequisites

#### Cloud Accounts

Before setting up your server you'll need to make sure you have your cloud accounts set up. If you're using Amazon then make sure you've enabled both S3 and SimpleDb.

* http://aws.amazon.com/simpledb/
* http://aws.amazon.com/s3/

#### Server Packages and Modules
Once you've confirmed that your cloud account is setup you can get started on your server. For that you'll need to have _Apache_, _PHP_ and _curl_ installed with a few modules.

    apt-get install apache2
    apt-get install php5
    apt-get install libapache2-mod-php5
    apt-get install php5-curl
    a2enmod rewrite

There are also a few optional but recommended packages and modules.

    apt-get install php5-imagick
    apt-get install exiftran
    a2enmod deflate
    a2enmod expires
    a2enmod headers

----------------------------------------

### Installing OpenPhoto

Download and install the source code. We recommend `/var/www/yourdomain.com` but you can use any directory you'd like.

#### Using git clone

    apt-get install git-core
    git clone https://github.com/photo/frontend.git /var/www/yourdomain.com
    chown -R www-data:www-data /var/www/yourdomain.com

#### Using tar

    cd /var/www
    wget https://github.com/photo/frontend/tarball/master -O openphoto.tar.gz
    tar -zxvf --group=www-data --owner=www-data openphoto.tar.gz
    mv openphoto-frontend-* yourdomain.com

----------------------------------------

### Setting up Apache and PHP

#### Apache

You'll need to copy the sample virtual host configuration file from the source to `/etc/apache2/sites-enabled`.

    cp /var/www/yourdomain.com/src/configs/openphoto-vhost.conf /etc/apache2/sites-enabled/

Now you'll need to replace instances of `/path/to/openphoto/html/directory` with `/var/www/yourdomain.com/src/html` or wherever you placed the code.

    vi /etc/apache2/sites-enabled/openphoto-vhost.conf

### PHP

You should also verify that your `php.ini` file has a few important values set correctly.

    vi /etc/php5/apache2/php.ini

Search for the following values and make sure they're correct.

    file_uploads = On
    upload_max_filesize = 16M
    post_max_size = 16M

Now you're ready to restart apache and visit the site in your browser.

    /etc/init.d/apache2 restart

### Launching your OpenPhoto site

Now you're ready to launch your OpenPhoto site. Point your browser to your host and you'll be taken to a setup screen. You'll need your cloud account credentials to continue.

Once you complete the 3 steps your site will be up and running and you'll be redirected there. The _setup_ screen won't show up anymore. If for any reason you want to go through the setup again you will need to delete the generated config file and refresh your browser.

    rm /var/www/yourdomain.com/src/configs/generated/settings.ini

**ENJOY!**