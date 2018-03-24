# SSH passwords

Using Teampass, it is possible to update a user password on a remote Linux server.

## Enable feature

Connected with an Administrator account, it is first required to enable this feature.

Select page `Settings` and tab `Options`.

Then enable it.

![](../img/feat-ssh-1.png)

## Do a one-shot change

	This feature permits to change a User password with a new one from Teampass.

To do this, follow next steps:

1. Select Item

![](../img/feat-ssh-2.png)

You must ensure that:

- `login` is the user login on this server
- `url` is with formalism: `ssh://<ip>:<port>`

2. Select `Update server passowrd` from the Item menu

![](../img/feat-ssh-3.png)

3. Select tab `One-time change`

![](../img/feat-ssh-4.png)

4. If this user doesn't have the privileges on the Linux server to update his passowrd, please provide the credentials with those priviles.

5. Click `Start` when ready to perform the change

![](../img/feat-ssh-6.png)

> In this previous screen capture, you can see that the SSH account used is the server root one.