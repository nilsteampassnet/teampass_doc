
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

`<LOGIN>;<NAME>;<LASTNAME>;<PASSWORD>;<EMAIL>;<ADMINISTRATEDBY>;<READ_ONLY>;<ROLE1,ROLE2,...>;<IS_ADMIN>;<ISMANAGER>;<PERSONAL_FOLDER>` has to be sent as a **base64 encoded string**. The separator symbol is the comma ` ; `.

*Some limitations*:

* `ADMINISTRATEDBY`, `READ_ONLY`, `IS_ADMIN`, `ISMANAGER`, `PERSONAL_FOLDER` are boolean and accept value `1` for `TRUE` and value `0` for `FALSE`.

# Generate a password

Generating a new password is done through URL:

```yaml
<url to teampass>/api/index.php/new_password/<size>;<secure>;<numerals>;<capitalize>;<ambiguous>;<symbols>;<base64 encoded string>?apikey=<VALID API KEY>
```

With:

* `<size>` an integer taken from 4 to 50
* `<secure>` takes `1` if secure password is expected, else it takes `0`
* `<numerals>` takes `1` if password can contain numerals, else it takes `0`
* `<capitalize>` takes `1` if password can contain capitalize letters, else it takes `0`
* `<ambiguous>` takes `1` if password can contain ambiguous letters, else it takes `0`
* `<symbols>` takes `1` if password can contain symbols, else it takes `0`
* `<base64 encoded string>` takes `1` if you want the password to be sent back in base64 encoding string. This is mandatory if you ask for symbols.

The format sent back is JSON.
```yaml
Example: {"password" : "Chohcee7phahTooThoh"}
```
If symbols are asked then password is base64 encoded
```yaml
Example: {"password" : "Y3VlM0hhaHlhaDlvaWomYWU0bw=="}
```

# Get the list of Complexicity levels

The list is sent back through URL:

```yaml
<url to teampass>/api/index.php/info/complexicity_levels_list?apikey=<VALID API KEY>
```

The format sent back is JSON.
```yaml
{
  "0": "Very weak",
  "25": "Weak",
  "50": "Medium",
  "60": "Strong",
  "70": "Very strong",
  "80": "Heavy",
  "90": "Very heavy"
}
```

# Return Folder information

The Folder information are obtain through URL:

```yaml
<url to teampass>/api/index.php/info/folder/<folder_id>?apikey=<VALID API KEY>
```

The format sent back is JSON.
```yaml
{
  "title": "Sub folder name",
  "personal_folder": "0",
  "renewal_period": "0",
  "parent_id": "1",
  "path": "Folder #1 > Sub folder name"
}
```

# API version

Get API version through URL:

```yaml
<url to teampass>/api/index.php/info/version?apikey=<VALID API KEY>
```

The format sent back is JSON.

```yaml
{
  "api-version": "2.0"
}
```