## Error 403 / 500, blank page, ...

Teampass comes with csrfProtector that protects against Cross Site Request Forgery mechanisms. Due to this, you must ensure that your Teampass configuration is consistent between all paths.

In this example, we will considere that Teampass is hosted at `https://my.domain.net/teampass`.

### Teampass settings

* Open the `Settings` page (https://my.domain.net/teampass/index.php?page=manage_settings)
* Fill in the four (4) URL fields with the correct URL the users will use.
![Screenshot](../img/error-1.png)

> Don't use any redirection. Use only the correct URL in those settings. Otherwize csrfProtector will considere this as an inconsistency and will raise an error.

### CSRFProtector settings

* With a shell, open file `<path to teampass folder>/includes/libraries/csrfp/libs/csrfp.config.php`
* Check variable `jsUrl`, it must contain the complete URL too.
![Screenshot](../img/error-2.png)
