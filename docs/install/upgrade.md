__Valid since 2.1.27 release__

# Upgrade Teampass to a new release

It is recommended to install the latest Teampass release when available.

---

# Upgrade protocol

The next described protocol is a recommended one.

* Create a dump of your database
* Perform a zip of the current Teampass folder
* Make a copy of teampass-seckey.txt (even if the upgrade process will perform one too)
* Download latest package on your server
* Unzip package into `Teampass` folder (could be another name) and overwrite existing files and folders,
* Enter url `http://your_domain/teampass/install/upgrade.php`
* Now follow the upgrade pages

## Step 1

It's an introduction page with some recommendations.

Log in using an _Administrator account_.

## Step 2

Some server checks are performed based upon the path. Please check that the path is correct before starting.

## Step 3

This page loads the database credentials from the file `/includes/config/settings.php`.
If you have performed changes, you will need to edit this file prior to continuing this step.

If a previous upgrade didn't stored the saltkey inside the database, a fieldset will appears asking you to enter it inside a specific password field.

> You need to write the saltkey that is inside the sk.php file.

## Step 4

This step permits the database update.

## Step 5

This step updates configuration files

## Done

Once the previous steps are done, Teampass is now upgraded.


---

# Upgrade from very old versions

The next chapters will provide some tips in order to upgrade since version 2.1.23.

## Upgrade to 2.1.23.4

- Run SQL query: ```ALTER TABLE `teampass_misc` ADD `id` INT(12) NOT NULL AUTO_INCREMENT FIRST, ADD PRIMARY KEY (`id`);```
- Rename the file `/install/upgrade_ajax.php` by `/install/upgrade_ajax_original.php`
- Get the file `upgrade_ajax_for_2.1.23.4.php`, store it in folder `/install` and rename it `/install/upgrade_ajax.php`
- Perform upgrade
- Check that everything works as expected (think to clear your browser cache)

## Upgrade to 2.1.24.4

- Before starting the upgrade, run the SQL query: ```ALTER TABLE `teampass_items` CHANGE `pw_len` `pw_len` INT(5) NOT NULL DEFAULT '0';
;```
- Perform upgrade
- Check that everything works as expected (think to clear your browser cache)

## Upgrade to 2.1.25.2

- Before starting the upgrade, run the SQL query: ```INSERT INTO `teampass_misc` (`id`, `type`, `intitule`, `valeur`) VALUES (NULL, 'admin', 'encryption_protocol', 'ctr');```
- Perform upgrade
- Check that everything works as expected (think to clear your browser cache)

## Upgrade to 2.1.26-final-3

- Perform upgrade
- Check that everything works as expected (think to clear your browser cache)


## Upgrade to 2.1.27.(latest)

- Before starting the upgrade, run the SQL query: ```ALTER TABLE `teampass_misc` CHANGE `id` `increment_id` INT(12) NOT NULL AUTO_INCREMENT;```
- Perform upgrade
- Check that everything works as expected (think to clear your browser cache)

Following those steps will permit your to get your data in the latest version of Teampass.