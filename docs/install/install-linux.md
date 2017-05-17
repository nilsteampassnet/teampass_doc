#  Install Teampass on a GNU/Linux server

The easiest way to install Teampass is to install LAMP dedicated to the GNU/Linux distribution you have. Refer to all the good tutorials existing to install Apache, MySQL (or MariaDB) and PHP.

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

# Prepare the database

Using phpMyAdmin web interface:

* Install phpMyAdmin, open its web interface
* Select tab called `Databases`
* In the `Create new database` section, enter your database name (for example `teampass`) and select `UTF8_general_ci` as collation.
* Click on `Create` button

Using command line, on a Debian GNU/Linux system:

* Install the mariadb-server package, specify a password when prompted to (consider using pwqgen from the passwdqc package to generate the password)
* Run the mysql_secure_installation to finish the initial installation
* Access your newly configured server (you'll be prompted for the database root password): <br/><pre># mysql -uroot -p</pre>
* Create the TeamPass database: <br/><pre>create teampass character set utf8 collate utf8_bin;</pre>

# Set the database Administrator

We will now create a specific Administrator to this database.

Using phpMyAdmin web interface:

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

*Using command line, on a Debian GNU/Linux system:*

* Access your newly configured server: <br/><pre># mysql -uroot -p</pre>
* Create the teampass_admin user, assigning it full rights to the TeamPass table: <br/><pre>grant all privileges on teampass.* to teampass_admin@localhost identified by 'PASSWORD';</pre>

# Setup SSL

* If your use of TeamPass will be limited to your LAN, on Debian systems, see https://wiki.debian.org/Self-Signed_Certificate
* If your TeamPass install will be on a public Internet system, consider using an SSL certificate from https://letsencrypt.org/ or from a commercial provider

# Get TeamPass

* Once your Apache server is running, download TeamPass from https://github.com/nilsteampassnet/TeamPass/releases (under Downloads, .zip file).
* Unzip the file into your localhost folder (by default it is `/opt/lampp/htdocs`) using command `unzip teampass.zip -d /opt/lampp/htdocs`.

Note:

* On CentOS systems, the default folder is `/var/html/www`
* On Debian systems, the default folder is 'var/www/html'

# Set folders permissions

* Open your terminal
* Point to htdocs folder `cd /opt/lampp/htdocs)` - see the note above about distribution-specific folders
* Enter the following commands
```
chmod -R 0777 teampass/includes/config
chmod -R 0777 teampass/includes/avatars
chmod -R 0777 teampass/includes/libraries/csrfp/libs
chmod -R 0777 teampass/includes/libraries/csrfp/log
chmod -R 0777 teampass/includes/libraries/csrfp/js
chmod -R 0777 teampass/backups
chmod -R 0777 teampass/files
chmod -R 0777 teampass/install
chmod -R 0777 teampass/upload
```

# Finish the TeamPass installation

Using your Browser, go to `https://localhost/teampass` or your specific domain, and follow the proposed steps 

Once installation is finished, you can use TeamPass on your GNU/Linux server.
