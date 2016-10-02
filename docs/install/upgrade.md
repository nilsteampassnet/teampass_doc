# Upgrade Teampass to a new release

It is recommended to install the latest Teampass release.

---

# Upgrade protocol

The next described protocol is a recommended one.

* Start by creating a dump of your database
* Rename the current Teampass folder (example: `Teampass_old`)
* Download lastest package on your server,
* Unzip package into `Teampass` folder (could be another name),
* Copy from `Teampass_old` to `Teampass` folder:
	* the file `/includes/config/settings.php`
	* the file `/includes/config/tp.config.php`
	* the folders `backups`, `files` and `upload`
* Enter url `http://your_domain/teampass/install/upgrade.php`
* Now follow the upgrade pages

# Step 1

It's an introduction page with some recommendations and the licence display.

# Step 2

Some server checks are performed based upon the path. Please check that the path is correct before starting.

	Be sure to check that Encryption Key is correct.

# Step 3

Check that the given database credentials are correct and permit Teampass to get connected to the database.

It is required to give the next credentials:

- **Server name** (ex: localhost)
- **Database name** (it is recommended to have a dedicated database for Teampass. Ex: teampass)
- **User** (it is recommended that this user has ROOT privileges on Teampass database) 
- **Password**
- **Tables prefix**

# Step 4

This step permits the tables creation and data copy.

A second part of this step consists in generating the Items keys if needed.

# Done

Once the previous steps are done, Teampass is now upgraded.