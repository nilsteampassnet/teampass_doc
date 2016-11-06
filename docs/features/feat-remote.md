
# Automatic password change on remote server

This feature permits to change the password of a remote server (only Linux) using an SSH connection. It is enabled through the Settings page.

# Principles

It works as described below.

* Based upon field `url` starting with prefix `ssh://`, the script knows what server to connect to.
* Based upon fields `login` and `password`, the script knows what credentials to use to update the remote server.

# Steps to proceed with

In order to activate the change of password directly on the related server, you need to follow next steps:

* Display the details of the Item in Teampass
* Select option `Update server's password`

![Screenshot](../img/feat-remo-1.png)

* A new dialogbox will be displayed
* You can select either `One shot change` or `scheduled change`
* Enter the credentials to permit the Teampass script to get authorize through SSH
* Launch the change

![Screenshot](../img/feat-remo-2.png)

![Screenshot](../img/feat-remo-3.png)


# What will happen?

Teampass will perform next things:

* Get connected to the remote server through SSH
* Generate a new automatic complexe password (if you decided to go on with automatic mode)
* Launch a linux command to change the password of the user
* Close SSH connection
* Store the new password in database (if you decided to go on with automatic mode)