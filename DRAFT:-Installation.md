Open Photo / Installation
=======================
#### OpenPhoto, a photo service for the masses

## OS: Linux Ubuntu Server 11.04
This is a description how to install the OpenPhoto in a linux ubuntu server.

### Checks
* Check if you have LAMP stack installed
 * if not, you can visit [[https://help.ubuntu.com/community/ApacheMySQLPHP]]

### Install OpenPhoto
* Clone the software
 * git clone https://github.com/openphoto/frontend.git

* Create a folder openphoto in your apache folder
 * e.g.: /var/www/openphoto

* Copy the files from the git repository to apache folder
 * cp -R {git_repository}/src /var/www/openphoto
  * Watch out with permission. You can use sudo.

* Open the setup screen in the browser
 * http://server_name/openphoto/views/setup.php

* Add Amazon credentials
 * Fill Amazon Access Key ID
 * Fill Amazon Secret Access Key

* Press, "Continue to Step 2"

