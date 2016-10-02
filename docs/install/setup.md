# Setup Teampass

Once Teampass is installed on your server, you need to go through some steps in order to setup Teampass and permit users to take advantage of this tool.

---

# Pre-requisite

Teampasshas to be installed on a server, and you require the `admin` account.

# Create Folders

The first step is to create Folders in which the Items will be added.
Those folders have to be organized in a logical way that fits your needs.

Refer to page [Manage Folders](../manage/manage-folders.md).

# Create Groups

The second step consists in two activities:

* create Groups in which your Users will be added
* set the access rights of Groups versus Folders

Refer to page [Manage Groups](../manage/manage-groups.md).

# Create Users

The third step consists in creating Users that will use Teampass.

You need to think about a global strategy relating the Folders, Groups and Users level.

Refer to page [Manage Users](../manage/manage-users.md).

# Administrator account

	Remember that an Administrator has no access to Items.

In order to test your set-up, it is recommended to create a dummy account user which you will use to test your Teampass configuration.

If for any reason, you want an Administrator to have access to Items and becoming a `normal user`, then you need to do the next change.

* Open file `include.php` in folder `/includes/config/`
* Change sentence `$k['admin_full_right'] = true;` to `$k['admin_full_right'] = false;`

Nevertheless, it is not a recommended way to do because the Administrator is in this case able to access any Items because he/she has access to all Rights configuration.
