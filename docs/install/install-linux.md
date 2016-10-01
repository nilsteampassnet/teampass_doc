#  Install Teampass on a Linux server

Easiest way to install Teampass is to install LAMP dedicated to the Linux distribution you have. Refer to all the good tutorials existing to install Apache, MySQL (or MariaDB) and PHP.

# Install PHP extensions

Ensure to install the expected extensions required by Teampass:

* `mcrypt`
* `mbstring`
* `openssl`
* `bcmath`
* `iconv`
* `gd`
* `mysqli_fetch_all`
* `xml`

# Prepare Database

* Open PhpMyAdmin
* Select tab called `Databases`
* In the `Create new database` section, enter your database name (for example `teampass`) and select `UTF8_general_ci` as collation.
* Click on `Create` button

# Get TeamPass

* Once your Apache server is running, download TeamPass.
* Unzip the file into your localhost folder (by default it is `/opt/lampp/htdocs`) using command `unzip teampass.zip -d /opt/lampp/htdocs`.

	In case of Centos, the default folder is `/var/html/www`.


# Set MySQL database Administrator

We will now create a specific Administrator to this database

* Click on `localhost` in order to get back to home page
* Select `Privileges` tab
* Click on `Add a new user` link
* Enter the login information (I suggest to create a user `teampass_admin` for better understanding of what is this user)
* Do not give any rights/privileges at this level of the user creation
* Click on `Go` button

Now it's time to set some privileges to this user.

* From Home page, click on `Privileges` tab
* Click on `Edit privileges` button corresponding to the `teampass_admin` user
* Click on `Check All` link
* Validate by clicking on button `Go`

# Set CHMOD on folders

* Open your terminal
* Point to htdocs folder `cd /opt/lampp/htdcos)`
* Enter commands
```
chmod -R 777 teampass/includes/config
chmod -R 777 teampass/includes/avatars
chmod -R 777 teampass/includes/libraries/csrfp/libs
chmod -R 777 teampass/includes/libraries/csrfp/log
chmod -R 777 teampass/includes/libraries/csrfp/js
chmod -R 777 teampass/backups
chmod -R 777 teampass/files
chmod -R 777 teampass/install
chmod -R 777 teampass/upload
```

# Install TeamPass

Using your Browser, go to `http://localhost/teampass` or your specific domain, and follow the several steps 

Once installation is finished, you can use TeamPass on your Linux server.