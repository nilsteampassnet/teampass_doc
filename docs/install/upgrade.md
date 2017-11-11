__Valid since 2.1.27 release__

# Upgrade Teampass to a new release

It is recommended to install the latest Teampass release.

---

# Upgrade protocol

The next described protocol is a recommended one.

* Create a dump of your database
* Perform a zip of the current Teampass folder
* Make a copy of teampass-seckey.txt (even if the upgrade process will perform one too)
* Download lastest package on your server,
* Unzip package into `Teampass` folder (could be another name) and overwrite existing files and folders,
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
