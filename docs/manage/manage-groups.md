# Manage the Groups

A Group contains a set of Users. It permits to ease the administration of access rights on Folders.
Indeed access rights on Folders are defined by Groups. 

A good practice is to organize the Users Group by team or groups of interest.

	Notice that a User may be associated to several Users Group.

# Example

Let's consider 3 Users (Us1, Us2 and Us3), 2 Folders (Fld1 and Fld2), and 2 Users Group (UG1 and UG2) defined as below:

* UG1 contains Us1, Us2 and Us3. It is associated to Fld2
* UG2 contains Us2. It is associated to Fld1

Based on this assumption, Us2 is the unique user to have access to both Fdl1 and Fld2.

# Access to Group Management page

Access to the `Group Management` page.

![Screenshot](../img/mng-grp-1.png)

# Creating a new Group

Click the icon `Add a Group`

![Screenshot](../img/mng-grp-2.png)

And fill in the form

![Screenshot](../img/mng-grp-3.png)

About the form:

* The label is the name of the Group.
* The `Required complexity` corresponds to the minimum password complexity level that a User password (that belong to this Group) needs to fulfil.

The new Group is now added to the list.

![Screenshot](../img/mng-grp-4.png)

# Edit a Group

To edit, click the `edition icon`.

![Screenshot](../img/mng-grp-5.png)

And edit it through the dialogbox

![Screenshot](../img/mng-grp-6.png)

# Delete a Group

To delete, click the `edition icon` and Confirm.

![Screenshot](../img/mng-grp-7.png)

	Users belonging to this Group will need to be associated to another Group.

# Using the rights matrix

The `rights matrix` permits to allow or not the access of Users in a Group to Folders.

To ease its understanding, the `rights matrix` uses colors and icons to indicate the specific rights set for a Group on a Folder.

* `Red` cell indicates that the Group is not allowed to access the folder
* `Yellow` cell indicates that the Group is allowed to View only
* `Green` cell indicates that the Group has access to the Folder
* `Blue` cell indicates that the Group has access to the Folder but with specific restrictions

Small icons permit to indicate the restrictions in place for a Group on a Folder.

![Screenshot](../img/mng-grp-8.png)

This matrix is very powerful and visible. As you can see in the previous screen-capture.

![Screenshot](../img/mng-grp-9.png)

# Allow access to all Items

This feature is disabled by default and is unsecure but it may be helpful.

It's aim is to permit the Users of a Group to have the right to edit/modify all Items they have access to.
It will bypass the settings set for each Item.

	Only activate this for a Group with limited Users.

To activate this, click on the icon as shown in next screen-capture.

![Screenshot](../img/mng-grp-10.png)

# Who can manage Groups

Creation, modification and deletion can only be performed by an Administrator or a Manager.

Notes:

* The Manager will only see the Group that he is associated to.
* Deleting a User Group will not delete the associated Users.
