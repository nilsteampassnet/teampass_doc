# Overview

The Teampass API permits an access to Teampass databse from a third party application.

The call is performed with a `GET` query and sends back the data at `json` format.

This page describes how to write data.

	"Note:" In this page, <valid api key> is the API key you received from your administrator.

# Add new Item

Adding a new Item is done through URL:

```yaml
<url to teampass>/api/index.php/add/item/<label>;<password>;<description>;<folder id>;<login>;<email>;<url>;<tags>;<any one can modify>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

*Some limitations*:

* `URL` should NOT include `http://`. Indeed this would break the initial url.
* `tags` field can be used for multiple tags and they need to be separated by a space.
* `any one can modify` is a boolean and accepts value `1` for `TRUE` and value `0` for `FALSE`.

Notice that if a similar Label exists, the add request will fail.

# Delete an Item

Deleting an Item is done through URL:

```yaml
<url to teampass>/api/index.php/delete/item/<item_id1>;<item_id2>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

The answer would be `OK` if succeeded or the error if failed.

# Delete a Folder

Deleting a Folder is done through URL:

```yaml
<url to teampass>/api/index.php/delete/folder/<folder_id1>;<folder_id2>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

The answer would be `OK` if succeeded or the error if failed.
