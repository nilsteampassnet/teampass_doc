
# Miscellaneous

This page describes some interesting services provided by the API.

---

# Authentication credentials for a web page

The API returns the `LOGIN` and `PASSWORD` based upon an `URL` sent in entry.

```yaml
<url to teampass>/api/index.php/auth/<PROTOCOL>/<URL>/<user login>/<user password>?apikey=<VALID API KEY>
```

With:

* `< PROTOCOL >` : is the protocol used for the URL (example: http|https|ftp|...)
* `< URL >` : is the URL without the protocol (example: http://www.teampass.net becomes www.teampass.net)
* `< user login >` : user's login
* `< user password >` : user clear password
* `< VALID API KEY >` : api key for access validation

```yaml
Example: https://127.0.0.1/teampass/api/index.php/auth/http/www.zadig-tge.adp.com/U1/test?apikey=chahthait5Aidood6johh6Avufieb6ohpaixain
```
 
The format sent back is JSON.
If several entries exist for one URL then all possibilities will be sent back.
 
```yaml
Example: {
	"<item_id>":{
    	"label":"<pass#1>",
        "login":"<login#1>",
        "pw":"<pwd#1>"
    },
    "<item_id>":{
    	"label":"<pass#2>",
        "login":"<login#2>",
        "pw":"<pwd#2>"
    }
}
```


# Add new User

Adding a new User is done through URL:

```yaml
<url to teampass>/api/index.php/add/user/<LOGIN>;<NAME>;<LASTNAME>;<PASSWORD>;<EMAIL>;<ADMINISTRATEDBY>;<READ_ONLY>;<ROLE1,ROLE2,...>;<IS_ADMIN>;<ISMANAGER>;<PERSONAL_FOLDER>?apikey=<VALID API KEY>
```
The separator symbol is the comma ` ; `.

*Some limitations*:

* `ADMINISTRATEDBY`, `READ_ONLY`, `IS_ADMIN`, `ISMANAGER`, `PERSONAL_FOLDER` are boolean and accept value `1` for `TRUE` and value `0` for `FALSE`.