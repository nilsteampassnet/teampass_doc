# Overview

The Teampass API permits an access to Teampass database from a third party application.

The call is performed with a `GET` query and sends back the data at `json` format.

This page describes how to read data.

> In this page, `<valid api key>` is the API key you received from your administrator.


# Read Folders

Reading the content of one or several Folders is performed by accessing the URL

```yaml
<url to teampass>/api/index.php/read/folder/<folder id>?apikey=<valid api key>
```

or

```yaml
<url to teampass>/api/index.php/read/folder/<folder id1>;<folder id2>;<folder id3>?apikey=<valid api key>
```
    
With

* `<folder id>` is the folder ID
* The separator symbol is the semi-column ` ; `

The format sent back is JSON.

```yaml
{
  "16": {
    "id": "16",
    "label": "Yahoo mail",
    "description": "Yahoo webmail",
    "login": "Itsme",
    "email": "itsme@yahoo.com",
    "url": "https://mail.yahoo.com",
    "pw": ",\"7@Y6^gC[",
    "folder_id": "5",
    "path": "Folder #1 > Sub folder name"
  },
  "2": {
    "id": "2",
    "label": "Motorola.com",
    "description": "Motorola customer portal",
    "login": "Jean-Paul",
    "email": "jp.maurice@gmail.com",
    "url": "https://www.motorola.com",
    "pw": "Motorola.com",
    "folder_id": "2",
    "path": "F2 - my new folder"
  }
}
```

# Read specific Items

To get the information about one specific Item, use URL

```yaml
<url to teampass>/api/index.php/read/items/<item id1>;<item id2>;<item id3>?apikey=<valid api key>
```

The separator symbol is the semi-column ` ; `.

With

* `<item idX>` is the item ID

The format sent back is JSON.

```yaml
{
  "2": {
    "id": "2",
    "label": "Motorola.com",
    "description": "Motorola customer portal",
    "login": "Jean-Paul",
    "email": "jp.maurice@gmail.com",
    "url": "https://www.motorola.com",
    "pw": "Motorola.com",
    "folder_id": "2",
    "path": "F2 - my new folder"
  },
  "16": {
    "id": "16",
    "label": "Yahoo mail",
    "description": "Yahoo webmail",
    "login": "Itsme",
    "email": "itsme@yahoo.com",
    "url": "https://mail.yahoo.com",
    "pw": ",\"7@Y6^gC[",
    "folder_id": "5",
    "path": "Folder #1 > Sub folder name"
  }
}
```

# Read user's items

To get all the items a user is allowed to access, use URL

```yaml
<url to teampass>/api/index.php/read/userpw/<user's login>?apikey=<valid api key>
```

The format sent back is JSON.

```yaml
{
  "16": {
    "id": "16",
    "label": "Yahoo mail",
    "description": "Yahoo webmail",
    "login": "Itsme",
    "email": "itsme@yahoo.com",
    "url": "https://mail.yahoo.com",
    "pw": ",\"7@Y6^gC[",
    "folder_id": "5",
    "path": "Folder #1 > Sub folder name"
  },
  "2": {
    "id": "2",
    "label": "Motorola.com",
    "description": "Motorola customer portal",
    "login": "Jean-Paul",
    "email": "jp.maurice@gmail.com",
    "url": "https://www.motorola.com",
    "pw": "Motorola.com",
    "folder_id": "2",
    "path": "F2 - my new folder"
  }
}
```


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
    "level": "1",
    "access_type": "NDNE"
  },
  {
    "id": "5",
    "title": "Sub folder name",
    "level": "2",
    "access_type": "W"
  },
  {
    "id": "22",
    "title": "A very long folder name",
    "level": "2",
    "access_type": "NDNE"
  },
  {
    "id": "23",
    "title": "teampass-connect",
    "level": "1",
    "access_type": "ND"
  },
  {
    "id": "24",
    "title": "An Edited folder 1",
    "level": "1",
    "access_type": "W"
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
  {
    "id": "3",
    "label": "yahoo",
    "description": "",
    "login": "nlaumaille@yahoo.fr",
    "email": "nlaumaille@yahoo.fr",
    "url": "https://login.yahoo.com/",
    "pw": "martin95",
    "folder_id": "2",
    "path": "F2 - my new folder",
    "status": "OK"
  },
  {
    "id": "13",
    "label": "Yaho test",
    "description": "Imported with Teampass-Connect",
    "login": "plouf",
    "email": "",
    "url": "https://login.yahoo.com/",
    "pw": "978qsd",
    "folder_id": "23",
    "path": "teampass-connect",
    "status": "OK"
  }
}
```
