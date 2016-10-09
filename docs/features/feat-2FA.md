
# Authentication

In order to access Teampass Items, a User has to be allowed to get connected. A User is authenticated through the usage of a `Login` and a `Password`.

The `Password` is encrypted in the database using Crypt feature which generates a hashed string using the standard Unix DES-based algorithm. The `Salt` used to generate this hash is obtained randomly with `openssl_random_pseudo_bytes` function.

It can be securized through usage of dedicated options defined here below.

# Normal access

As written previously, the initial level of authenication relies on the couple `Login` and a `Password`. This means that the user needs to indicate his credentials to get connected.

	Notice that 3 wrong attempts will disable the login feature during a period of 10 seconds.

# Securize login with Google Two-Factors

An option permits to enable `Google Two-Factors` to complete the initial login process.

Google two-factor authentication enhances logon security. When logging in, a QR code is displayed, which must be scanned into the user's Google Authentication app to receive a one-time password. 

	This requires all users to have Google authentication aplication on an Internet-connected mobile device.

# Securize login with DUOSecurity

## About DUOSecurity

DUOSecurity is a 2 factor authentication tool securizing any kind of tool requiring a usser authentication. It protects every account with ease.

For complete description, you should refer to [DUOSecurity.com](DUOSecurity.com) website.

## How does it work with Teampass?

Once enabled, this feature will require you to synchronize the accounts in Teampass and DUOSecurity. Each Teampass user login needs to have a similar input inside DUOSecurity.

When a Teampass user will require an access to Teampass, DUOSecurity will check if he/she is allowed to access and he/she will need to confirm the access through a dedicated and personal device (check the [authentication methods](https://www.duosecurity.com/product/methods)). If DUOSecurity confirms the legitimity of the user, then Teampass will allow the user to get connected.


## Define a specific application for your Teampass instance

How to create the DUOSecurity application for your Teampass instance.

 * Get connected to your DUOSecurity dashboard
 * Select `Applications` in the menu
 * Click button `Protect an Application`
 * In the list, select `Web SDK` and click `Protect this application`
 * Give a name to this application (example: Teampass)
 * The next settings could be selected:
   * `Username normalization` set to `none`
   * `New user policy` set to `Require Enrollment`
 * Click button `Save changes`
 
 Store the IKEY, SKEY and Host. You will need them in Teampass.
 
## Create the users
 
Inside the DUOSecurity interface select the Users menu and create a new user for each user you have in Teampass.
 
	You must ensure that the speling is exactly similar.
 
 ## Enable DUOSecurity in Teampass
 
  * Login in Teampass with an Administrator account.
  * Open `Settings` page
  * Select tab `2FA options`
  * Enable `DuoSecurity` by selecting option `Yes`
  * Generate a random key for `AKEY`
  * Fill in `IKEY`, `SKEY` and `HOST` with the credentials from the application you previously created in DUOSecurity dashboard.
  * Click button `Save data in sk.php file`
  
  Now your users will have to connect by indicating their login and password, and through DUOSecurity (and especially `DuoPush` feature) to get authenticated in Teampass.

# Securize login with AGSES

[agses.net](https://agses.net/)

> Planned to be developped in 2.1.27
