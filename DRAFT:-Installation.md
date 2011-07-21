Open Photo / Installation
=======================
#### OpenPhoto, a photo service for the masses

## OS: Linux Ubuntu Server 11.04
This is a description how to install the OpenPhoto in a linux ubuntu server.

----------------------------------------

### Prerequisites

You'll need to have _Apache_, _PHP_ and _curl_ installed with a few modules.

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

Download and install the source code. We recommend =/var/www/yourdomain.com= but you can use any directory you'd like.

#### Using git clone

    apt-get install git-core
    git clone https://github.com/openphoto/frontend.git /var/www/yourdomain.com
    chown -R www-data:www-data /var/www/yourdomain.com

#### Using tar

    cd /var/www
    wget https://github.com/openphoto/frontend/tarball/master -O openphoto.tar.gz
    tar -zxvf --group=www-data --owner=www-data openphoto.tar.gz
    mv openphoto-frontend-* yourdomain.com

----------------------------------------

### Setting up Apache

You'll need to copy the sample virtual host configuration file from the source to =/etc/apache2/sites-enabled=.

    cp /var/www/yourdomain.com/src/configs/openphoto-vhost.conf /etc/apache2/sites-enabled/

Now you'll need to replace instances of =/path/to/openphoto/html/directory= with =/var/www/yourdomain.com/src/html= or wherever you placed the code.

    vi /etc/apache2/sites-enabled/openphoto-vhost.conf

Now you're ready to restart apache and visit the site in your browser.

    /etc/init.d/apache2 restart

Go to your domain or hostname and you'll see the setup screen.

 * http://yourdomain.com/

* Add Amazon credentials
 * Fill Amazon Access Key ID
 * Fill Amazon Secret Access Key

* Press, "Continue to Step 2"

