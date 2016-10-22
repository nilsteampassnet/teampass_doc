# Overview

The Teampass API permits an access to Teampass database from a third party application.

The call is performed with a `GET` query and sends back the data at `json` format.

This page describes how to read data.

    In this page, `<valid api key>` is the API key you received from your administrator.


# Read one Folder

Reading the content of a Folder is performed by accessing the URL

```yaml
<url to teampass>/api/index.php/read/category/<folder id>?apikey=<valid api key>
```
    
With

* `<folder id>` is the folder ID

The format sent back is JSON.

```yaml
{
	"1":{
		"label":"I1",
		"login":"",
		"pw":"&XZcww1",
		"url":"http://teampass.net"
	},
	"2":{
		"label":"Google",
		"login":"Me",
		"pw":"nid6YA$B",
		"url":"http://teampass.net"
	}
}
```

# Read several Folder

Reading the content of several Folders is performed by accessing the URL

```yaml
<url to teampass>/api/index.php/read/category/<folder id1>;<folder id2>;<folder id3>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

With

* `<folder idX>` is the folder ID

The answer would be exactly the same as in the previous example.

# Read specific Items

To get the information about one specific Item, use URL

```yaml
<url to teampass>/api/index.php/read/items/<item id1>;<item id2>;<item id3>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

With

* `<item idX>` is the item ID

The answer would be exactly the same as in the previous example.

# Read user's items

To get all the items a user is allowed to access, use URL

```yaml
<url to teampass>/api/index.php/read/userpw/<user's login>?apikey=<valid api key>
```

The answer would be exactly the same as in the previous example.


# Read user's folders

To get all the folders a user is allowed to access, use URL

```yaml
<url to teampass>/api/index.php/read/userfolders/<user's login>?apikey=<valid api key>
```

The format sent back is JSON.

```yaml
{
  {
    "id": "2",
    "title": "F2 - my new folder",
    "level": "1"
  },
  {
    "id": "5",
    "title": "Sub folder name",
    "level": "2"
  },
  {
    "id": "22",
    "title": "A very long folder name",
    "level": "2"
  },
  {
    "id": "23",
    "title": "teampass-connect",
    "level": "1"
  }
}
```

# Find items

Search for items is performed with  URL

```yaml
<url to teampass>/api/index.php/find/item/<folder id1>;<folder id2>/<searched string>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

With

* `<folder idx>` is the folder ID
* `<searched string>` is the string searched

The answer would be

```yaml
{
	"1":{
		"id":"12",
		"label":"Google.com",
		"login":"Bob",
		"pw":"&XZcww1`",
		"url":"https://www.google.com",
		"folder_id":"12",
		"status":"OK"
	},
	"2":{
		"id":"25",
		"label":"Teampass",
		"login":"Jane",
		"pw":"&sdcww1`",
		"url":"http://teampass.net",
		"folder_id":"22",
		"status":"OK"
	}
}
```
