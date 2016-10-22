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

# Update an Item

Updating an existing Item is done through URL:

```yaml
<url to teampass>/api/index.php/update/item/<item_id>/<label>;<password>;<description>;<folder_id>;<login>;<email>;<url>;<tags>;<any one can modify>?apikey=<valid api key>
```

With `<label>;<password>;<description>;<folder_id>;<login>;<email>;<url>;<tags>;<any one can modify>` send as a **base64 encoding** string.
The separator symbol is the semi-column ` ; `.

Example:
```yaml
<url to teampass>/api/index.php/update/item/2/TW90b3JvbGEuY29tO01vdG9yb2xhLmNvbTtNb3Rvcm9sYSBjdXN0b21lciBwb3J0YWw7MjtKZWFuLVBhdWw7anAubWF1cmljZUBnbWFpbC5jb207aHR0cHM6Ly93d3cubW90b3JvbGEuY29tO3Rlc3QgbW90b3JvbGEgcG9ydGFsIGN1c3RvbWVyOzA?apikey=eevu1Aed0aiN4Phee9xaeshu2athool3iek2ahy
```
where the base64 encoded string is made of `Motorola.com;Motorola.com;Motorola customer portal;2;Jean-Paul;jp.maurice@gmail.com;https://www.motorola.com;test motorola portal customer;0`.

# Delete an Item

Deleting an Item is done through URL:

```yaml
<url to teampass>/api/index.php/delete/item/<item_id1>;<item_id2>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

The answer would be `OK` if succeeded or the error if failed.

# Add new Folder

Adding a new Folder is done through URL:

```yaml
<url to teampass>/api/index.php/add/folder/<title>;<complexity_level>;<parent_id>;<renewal_period>;<personal>?apikey=<valid api key>
```

With:

* `<title>;<complexity_level>;<parent_id>;<renewal_period>;<personal>` send as a **base64 encoding** string.
The separator symbol is the semi-column ` ; `.
* `<complexity_level>` is selected between the next values `[0, 25, 50, 60, 70, 80, 90]`
* `<personal>` takes `0` if public. It takes `1` if it is a personal folder, and in this case `<title>` must be `<user_id>`.
* `<parent_id>` takes `0` if it is `root level`.

> Notice that Users will not have access to this new folder. It will be requested to set the expected access rights on it.

# Update a Folder

Updating an existing Folder is done through URL:

```yaml
<url to teampass>/api/index.php/update/folder/<folder_id>/<title>;<complexity_level>;<renewal_period>?apikey=<valid api key>
```

With:

* `<title>;<complexity_level>;<renewal_period>` send as a **base64 encoding** string. The separator symbol is the semi-column ` ; `.
* `<complexity_level>` is selected between the next values `[0, 25, 50, 60, 70, 80, 90]`

# Delete a Folder

Deleting a Folder is done through URL:

```yaml
<url to teampass>/api/index.php/delete/folder/<folder_id1>;<folder_id2>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

The answer would be `OK` if succeeded or the error if failed.
