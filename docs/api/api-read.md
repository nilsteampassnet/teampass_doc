# Overview

The Teampass API permits access to the Teampass database from a third party application.

The call is performed with a `GET` query and sends back the data in `JSON` format.

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
* The separator symbol is the semicolon ` ; `

The response format is JSON.

```yaml
{
  {
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

# Read specific Items

To get the information about one specific Item, use URL

```yaml
<url to teampass>/api/index.php/read/items/<item id1>;<item id2>;<item id3>?apikey=<valid api key>
```

The separator symbol is the semicolon ` ; `.

With

* `<item idX>` is the item ID

The response format is JSON.

```yaml
{
  {
    "id": "3",
    "label": "yahoo",
    "description": "",
    "login": "nils@yahoo.fr",
    "email": "nils@yahoo.fr",
    "url": "https://login.yahoo.com/",
    "pw": "9&EzzpM90@d7",
    "folder_id": "2",
    "path": "F2 - my new folder"
  },
  {
    "id": "20",
    "label": "Webdealauto",
    "description": "Imported with Teampass-Connect",
    "login": "nils@yahoo.fr",
    "email": "",
    "url": "http://www.webdealauto.com/fr",
    "pw": "odO@s'23E",
    "folder_id": "23",
    "path": "teampass-connect"
  }
}
```

# Read user's items

To get all the items a user is allowed to access, use URL

```yaml
<url to teampass>/api/index.php/read/userpw/<user's login>?apikey=<valid api key>
```

The response format is JSON.

```yaml
{
  "1": {
    "id": "1",
    "label": "DNS server",
    "description": "For all DNS management",
    "login": "Admin",
    "email": "admin@dns.fr",
    "url": "http://mydns.fr",
    "pw": "Ud9r^ G7",
    "folder_id": "1",
    "path": "Folder #1"
  },
  "5": {
    "id": "5",
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

The response format is JSON.

```yaml
{
  "2": {
    "id": "2",
    "title": "My new folder",
    "level": "1",
    "access_type": "NDNE"
  },
  "5": {
    "id": "5",
    "title": "Sub folder name",
    "level": "2",
    "access_type": "W"
  },
  "22": {
    "id": "22",
    "title": "A very long folder name",
    "level": "2",
    "access_type": "W"
  }
}
```

# List items's file attachments

To get all the files attached to an item, use URL

```yaml
<url to teampass>/api/index.php/read/listfiles/<item_id>?apikey=<valid api key>
```

The response format is JSON.

```yaml
{
  "1" : {
      "id"     : "1",
      "type" : "image/jpeg",
      "name" : "image.jpg",
      "extension" : "jpg",
      "size" : "47314"
   },
   "2" : {
      "id"     : "2",
      "name" : "text.txt",
      "type" : "text/plain",
      "size" : "50546",
      "extension" : "txt"
   },
   "3" : {
      "id"     : "3",
      "name" : "image2.jpg",
      "type" : "image/jpeg",
      "size" : "46911",
      "extension" : "jpg"
   }
}
```

# Download items's file attachments

To download a file attached to an item, use URL

```yaml
<url to teampass>/api/index.php/read/files/<file_id>?apikey=<valid api key>
```

```yaml
Example: curl -X GET "https://127.0.0.1/teampass/api/index.php/read/files/32?apikey=chahthait5Aidood6johh6Avufieb6ohpaixain" -o file.txt
```

The response format is binary file data.

# Find items

Search for items is performed with URL

```yaml
<url to teampass>/api/index.php/find/item/<folder id1>;<folder id2>/<searched string>?apikey=<valid api key>
```

The separator symbol is the semicolon ` ; `.

With

* `<folder idx>` is the folder ID
* `<searched string>` is the string searched

The response would be

```yaml
{
  {
    "id": "3",
    "label": "yahoo",
    "description": "",
    "login": "nils@yahoo.fr",
    "email": "nils@yahoo.fr",
    "url": "https://login.yahoo.com/",
    "pw": "Po9_T5rte3",
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
