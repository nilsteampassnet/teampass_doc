__Valid since 2.1.27 release

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

It's an introduction page with some recommendations.

Get logged using an _Administrator account_.

# Step 2

Some server checks are performed based upon the path. Please check that the path is correct before starting.

# Step 3

This page loads the database credentials from the file `/includes/config/settings.php`.
If you have performed changes, you need to edit this file priori to continue this step.

If a previous upgrade didn't stored the saltky inside the database, a fieldset will appears asking you to enter it inside a specific password field.

> You need to write the saltkey that is inside the sk.php file.

# Step 4

This step permits the database update.

# Step 5

This step updates configuration files

# Done

Once the previous steps are done, Teampass is now upgraded.
