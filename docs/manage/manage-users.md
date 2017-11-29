
# Roles in Teampass

Teampass uses 3 roles of possible Users.

## Administrator

The Administrator has to set up Teampass to fit the expectations in term of features.
In order to achieve this goal, his role is to:

* Set the expected options
* Manage the [Folders](./manage-folders.md) (creation, modification and deletion)
* Manage the [Groups](./manage-groups.md) (creation, modification and deletion)
* Manage the Users (creation, modification and deletion)

An Administrator can perform any kind of operation in Teampass except working on Items.

The Administrator is often a member of IT team.

Notice that the Administrator has not access to the Items with his "administrator" account.

## Manager

A Manager in Teampass is a super user that can:

* manage [Folders](./manage-folders.md) (creation, modification and deletion) associated to the [Groups](./manage-groups.md) he belongs to
* manage Users (modification and deletion) on which he is defined as "main administrator"
* of course, deal with Items

A Manager could be a Team leader.

## Human Resources

A Human Resources Manager in Teampass has the same rights as a Manager but he can manage all Users independately of his/her group. 

Notice that he will be also promoted to Manager role, and that he will not be able to edit existing administrators.

## User

A User is a normal Teampass user which deals with Items in the way defined by the Administrator and Manager.

# Access to Users Management page

Access to the `Users Management` page.

![Screenshot](../img/mng-usr-1.png)

# Add a new User

Click the icon `Add a User`

![Screenshot](../img/mng-usr-2.png)

And fill in the form

![Screenshot](../img/mng-usr-3.png)

About the form:

* `Name`, `Last name` and `Login` need to be filled in.
* The `Password` is the one the User will need to use to get connected to Teampass.
* `Email` is used to some specific feature of Teampass.
* `User is administrated by` setting is important. By default, Administrators will manage the Users, but you can also decide that this management could be delegated to the Manager of a Role. In this case, select the Role manager.
* Next 3 settings `Is admin`, `Is Manager` and `Is read only` are related to the permission of the User inside Teampass. 
* If `Personal folder` is ticked, then the Personal Folder for this User will be created.
* If `Create folder and role for ***` is ticked, then you can imagine what will happen.

The new User is now added to the list.

![Screenshot](../img/mng-usr-4.png)

You now need to associate this new User to one or more Groups. Click on the `Edit icon` at the left of the User.

![Screenshot](../img/mng-usr-5.png)

Perform the change you want on this User using the dialog box that appears.

![Screenshot](../img/mng-usr-6.png)

With:

* `Groups` field permits you to select the Groups that this user belongs to
* `Managed by` field permits you to select what Manager (or Administrator) will manage this user.
* `Allowed Folders` field permits you to select Folders to which the User will have access even if not allowed by the Groups he is associated to (see next chapter for more explanations)
* `Denied Folders` field permits you to select Folders to which the User will NOT have access even if allowed by the Groups he is associated to (see next chapter for more explanations)

# Allowed and Forbidden Folders

Each user is associated to Groups. This means he/she can access the Folders defined through the Group.

Nevertheless you can decide to allow this User to access other Folders than the one allowed by the Group.
For this, you need to use setting `Allowed Folders`.

You can also decide to restrict the access to some Folders using the setting `Forbidden Folders`.

	This should be very rare and for specific case. If it is regularly used, you should think about arranging your Roles.

# Lock and Delete a User

For some reason, you could need to lock a User. This will prevent the User from connecting to Teampass.

![Screenshot](../img/mng-usr-7.png)

When a user is locked, this red icon appears at the left:

![Screenshot](../img/mng-usr-8.png)

You can only `delete` a User that has been previously `locked`. For this, tick the corresponding checkbox and save.

![Screenshot](../img/mng-usr-9.png)

To `unlock` a locked User, tick the corresponding checkbox and save.

![Screenshot](../img/mng-usr-10.png)

# Change the User role

You can change the User level by using the selectors.

![Screenshot](../img/mng-usr-11.png)

The Users Levels are:

* `Is Admin`: tick (1) to change the User to Administrator
* `Is Manager`: tick (2) to change the User to Manager
* `Is Read Only`: tick (3) to change the User to become Read Only
* `Is Human Resources`: tick (4) to change the User to Human Resources Manager

# Special actions

Using the selectors, you can quickly perform the following actions on a User.

![Screenshot](../img/mng-usr-12.png)

* Allow to `create folders on Root level`
* Enable or disable `Personal Folders`
* Change the User's `Password`
* Change the User's `Email`
* See the `Log`
