# Overview

The Teampass API permits access to a Teampass database from a third party application.

The call is performed with a `GET` query and sends back the data in `JSON` format.

This page describes how to write data.

	"Note:" In this page, <valid api key> is the API key you received from your administrator.

# Information about base64_enconding

Sent data is done through usage of base64 encoded data.

Nevertheless you muse ensure that the encoded data doesn'`include the chatacters ` + ` and ` / `. 
They need to be replace by ` - ` and ` _ `.
This will guarantee that the URL sent is not broken by a reserved characted inside the URL.

Consequence: Please ensure that the substitution is performed inside the base64 encoded string:

- ` + ` is replaced by ` - `
- ` / ` is replaced by ` _ `

# Add new Item

Adding a new Item is done through URL:

```yaml
<url to teampass>/api/index.php/add/item/<label>;<password>;<description>;<folder id>;<login>;<email>;<url>;<tags>;<any one can modify>?apikey=<valid api key>
```

`<label>;<password>;<description>;<folder id>;<login>;<email>;<url>;<tags>;<any one can modify>` send as a **base64 encoding** string.
The separator symbol is the semicolon ` ; `.

*Some limitations*:

* `tags` field can be used for multiple tags and they need to be separated by a space.
* `any one can modify` is a boolean and accepts value `1` for `TRUE` and value `0` for `FALSE`.

Notice that if a similar Label exists, the add request will fail.

The response body looks like this:

```yaml
{
	"status" : "item added",
    "new_item_id" : "54"
}
```

# Update an Item

Updating an existing Item is done through URL:

```yaml
<url to teampass>/api/index.php/update/item/<item_id>/<label>;<password>;<description>;<folder_id>;<login>;<email>;<url>;<tags>;<any one can modify>?apikey=<valid api key>
```

With `<label>;<password>;<description>;<folder_id>;<login>;<email>;<url>;<tags>;<any one can modify>` send as a **base64 encoding** string.
The separator symbol is the semicolon ` ; `.

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

The separator symbol is the semicolon ` ; `.

The response body will contain `OK` if the request is successful. If the request is unsuccessful, the response body will contain an error message.

# Add new Folder

Adding a new Folder is done through URL:

```yaml
<url to teampass>/api/index.php/add/folder/<title>;<complexity_level>;<parent_id>;<renewal_period>;<personal>?apikey=<valid api key>
```

With:

* `<title>;<complexity_level>;<parent_id>;<renewal_period>;<personal>` send as a **base64 encoding** string.
The separator symbol is the semicolon ` ; `.
* `<complexity_level>` is selected between the next values `[0, 25, 50, 60, 70, 80, 90]`
* `<personal>` takes `0` if public. It takes `1` if it is a personal folder, and in this case `<title>` must be `<user_id>`.
* `<parent_id>` takes `0` if it is `root level`.

> Notice that Users will not have access to this new folder. It will be requested to set the expected access rights on it.

The answer sent back looks like this:

```yaml
{
	"status" : "folder created",
    "new_folder_id" : "54"
}
```

# Update a Folder

Updating an existing Folder is done through URL:

```yaml
<url to teampass>/api/index.php/update/folder/<folder_id>/<title>;<complexity_level>;<renewal_period>?apikey=<valid api key>
```

With:

* `<title>;<complexity_level>;<renewal_period>` send as a **base64 encoding** string. The separator symbol is the semicolon ` ; `.
* `<complexity_level>` is selected between the next values `[0, 25, 50, 60, 70, 80, 90]`

# Delete a Folder

Deleting a Folder is done through URL:

```yaml
<url to teampass>/api/index.php/delete/folder/<folder_id1>;<folder_id2>?apikey=<valid api key>
```

The separator symbol is the semicolon ` ; `.

The response body will contain `OK` if the request is successful. If the request is unsuccessful, the response body will contain an error message.
