# Frequentely Asked Question

The FAQ page helps you with classical questions you may have.

---


#### How to set Teampass under Maintenance?
* Open `Settings` page	
* Spot `Set TeamPass in Maintenance mode` option	
* Enable it
* Save

#### I don't see the Import button

The main reason for getting a blank/white page after installation is related `include.php` file.
Follow next steps to ensure every settings are correct in this file.

* Open file `includes\include.php` with your favourite editor	

#### Why a blank page after installation?

The main reason for getting a blank/white page after installation is related `include.php` file.
Follow next steps to ensure every settings are correct in this file.

* Open file `includes\include.php` with your favourite editor	

#### Line 14 @define('SECUREPATH', ...)

It defines the path to the secured folder you have indicated during installation.

!!! Note

	Be careful to not add an end slash.
	

* On a `Windows server`, it could be defined as
`
@define('SECUREPATH', 'E:\xampp\security\Teampass');
`
	
* On a `Linux server`, it could be defined as
`
@define('SECUREPATH', '/var/services/web/security/teampass');
`

#### Line 15 require_once ...

It loads the sk.php file when using Teampass.

!!! Note

    It is mandatory to indicate here the correct path to `sk.php` file.

* On a `Windows server`, it could be defined as
`
require_once "E:/xampp/security/teampass/sk.php";
`
	
* On a `Linux server`, it could be defined as
`
require_once "/var/services/web/security/teampass/sk.php";
`