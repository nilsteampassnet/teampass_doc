# Install Teampass on a Windows server

In order to install TeamPass on a Windows server, you need to first have an Apache server with MySql and PHP. 
You can either install each of those components one by one, or directly use a full 'All in One' package such as Xampp, WampServer, etc.

	In this case, we are using WampServer.

# Install your Apache server

* Download the last version of WampServer
* Launch installation (you can follow installation directly from the Help page of the editor)
* Once installed, start your server and you should see the wampserver icon in green. As shown in next screen capture.

# Activate PHP extensions

* Click on the WampServer icon
* In the dialog box, select `PHP > PHP extensions` and enable each of the following extensions:
  * `mcrypt`
  * `mbstring`
  * `openssl`
  * `bcmath`
  * `iconv`
  * `gd`
  * `mysqli_fetch_all`
  * `xml`

## Set MySQL database Administrator

* Open PhpMyAdmin (click on the WampServer icon and select PhpMyAdmin)
* In the 'Create new database' section, enter your database name (for example 1teampass`) and select `UTF8_general_ci` as collation.
* Click on `Create` button

#Set MySQL database Administrator

We'll now create a specific Administrator for this database

* Click on 'localhost' in order to get back to home page
* Select 'Privileges' tab
* Click on 'Add a new user' link
* Enter the login information (I suggest to create a user `teampass_admin` for better understanding of what is this user)
* Do not give any rights/privileges at this level of the user creation
* Click on 'Go' button

Now it's time to set some privileges to this user.

* From Home page, click on `Privileges` tab
* Click on 'Edit privileges' button corresponding to the `teampass_admin` user
* Click on 'Check All' link
wampserver_green
Create database
Edit privileges of user
Set privileges to user

* Validate by clicking on button `Go`

# Upload files

* Download TeamPass package
* Unzip it in a temporary folder
* If your installation is a local one, copy the folder TeamPass in folder `<wampserver_installation_path>/www`. If it is a remote server, use your FTP software to upload the TeamPass folder in `html_public` folder

# Ready to install TeamPass

* With your favorite web browser, get to `http://<your_teampass_url>`
* Follow instructions given by the installation script

# On IIS server be sure to use slashes in path

During the setup wizard, use C:/www/website and also c:/path-to-salt rather than c:\path-to-salt or c:\www\website.
