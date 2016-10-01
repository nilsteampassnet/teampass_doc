# Overview

The Teampass API permits an access to Teampass databse from a third party application.

The call is performed with a `GET` query and sends back the data at `json` format.

This page describes how to write data.

	"Note:" In this page, <valid api key> is the API key you received from your administrator.

# Add new Item

Adding a new Item is done through URL:

```yaml
<url to teampass>/api/index.php/add/item/<label>,<password>,<description>,<folder id>,<login>,<email>,<url>,<tags>,<any one can modify>?apikey=<valid api key>
```

The separator symbol is the comma ` , `.

*Some limitations*:

* `URL` should NOT include `http://`. Indeed this would break the initial url.
* `tags` field can be used for multiple tags and they need to be separated by a space.
* `any one can modify` is a boolean and accepts value `1` for `TRUE` and value `0` for `FALSE`.

Notice that if a similar Label exists, the add request will fail.

# Add new User

Adding a new User is done through URL:

```yaml
<url to teampass>/api/index.php/add/user/<LOGIN>;<NAME>;<LASTNAME>;<PASSWORD>;<EMAIL>;<ADMINISTRATEDBY>;<READ_ONLY>;<ROLE1,ROLE2,...>;<IS_ADMIN>;<ISMANAGER>;<PERSONAL_FOLDER>?apikey=<VALID API KEY>
```
The separator symbol is the comma ` ; `.

*Some limitations*:

* `ADMINISTRATEDBY`, `READ_ONLY`, `IS_ADMIN`, `ISMANAGER`, `PERSONAL_FOLDER` are boolean and accept value `1` for `TRUE` and value `0` for `FALSE`.