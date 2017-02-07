
# Items

The main page is the one the users will access and handle the Items.

![Screenshot](../img/feat-item-2.png)

The main screen is devided in 3 main parts. Each of those parts has its own sub menu which allows to perform specific actions on Folders and Items.

# Folders tree

The `Folders Tree` shows the folders the user is allowed to see and access.

> Click a Folder to see the related Items.

Clicking the Folders Menu brings up a list of possible actions. The actions list is depending on the enabled options.

![Screenshot](../img/feat-item-3.png)

# Items list

Contains the Items stored in the selected Folder. The list shows the Item label and the Description. For each Item, small icons are displayed permitting to quickly perform actions on the items such as copying in clipboard `Password` and `Login` (if enabled).

![Screenshot](../img/feat-item-4.png)

If allowed to, the user can make a drag and drop to move the Item to another folder.

# Item details

Displays the details for the selected Items.

![Screenshot](../img/feat-item-5.png)

The Item detail area permits the user to see all data related to an Item.


# Searching Items

You can perform a search inside a specific page.

![Screenshot](../img/feat-item-6.png)

The Items are shown in a table format in which you can perform a search using a criteria. This criteria performs the search inside several fields.

![Screenshot](../img/feat-item-7.png)

# Attach files to Item

You can attach files to your item. In case it is an image, Teampass displays it through a Viewer.

![Screenshot](../img/feat-item-10.png)

To attach files,

* select tab `Files & Images`

![Screenshot](../img/feat-item-8.png)

* Click `Select` and select the files to attach
* Click `Start file upload` to upload the selected files.

![Screenshot](../img/feat-item-9.png)

* Now save

Several options can be defined by Administrator to fit security rules.
It is possible to:

* limit the files extension 
* limit the maximum size of an attached file
* resize the image

![Screenshot](../img/feat-item-11.png)

# Delete an Item

You can delete an Item. To do so:
* select the Item
* do a click on the top Item menu button
* select "Delete item"

![Screenshot](../img/feat-item-12.png)

* confirm deletion

![Screenshot](../img/feat-item-13.png)

> A Deleted item is only disabled and not deleted from the database. It is possible to restore it unless it has been purged.

# Restore an Item

A deleted item can be either restore back to its previous position, either purged away.

To do so:
* be logged as a Manager or Administrator
* select `Utilities` view

![Screenshot](../img/feat-item-14.png)

* select tab `Deletion`
* select the Items to Restore or Delete
* click button corresponding to your choice

![Screenshot](../img/feat-item-15.png)

> If you decide to Delete, the selected Items will be purged from the database.

> If you decide to Restore, the selected items will be restored at their previous position.

# Mass move & delete

[Introduced in 2.1.27]

Mass operation permits to select a set of Items and perform a common action on them. Currently, you may either `Move` or `Delete` a selection of Items.

This feature is only allowed if the setting `Allow user to perform massive move and delete operations` is set to **Yes**.

Performing mass operation is possible from the page called `Find`.

![Screenshot](../img/feat-item-16.png)

When the user has the right to either move or delete an item, a checkbox is added in front of its label.

![Screenshot](../img/feat-item-17.png)

You may select as many items you want.

Using the icons, you can decide to launch the action you want.

![Screenshot](../img/feat-item-18.png)

## Moving items

Select the destination folder and click on OK button.

![Screenshot](../img/feat-item-19.png)

Wait until the dialogbox is closed.

## Deleting items

Confirm the deletion by clicking on OK button.

![Screenshot](../img/feat-item-20.png)

Wait until the dialogbox is closed.

# Suggest an Item change

[Introduced in 2.1.27]

Suggesting a change on an existing item is possible. The user may suggest a change for `Label`, `Password`, `Login`, `Email` and `Url`.

## Making a change proposal

Select the Item on which the change proposal has to be made

![Screenshot](../img/feat-item-21.png)

Change the fields you are interested in. You may also add a comment that will help the Manager to know the context of the proposal.

![Screenshot](../img/feat-item-22.png)

Click to confirm your proposal. An email is sent to the Managers to warn about a new proposal.

## Approving / Rejecting a change proposal

Once created, the change proposal is stored in database. When the user is a Manager, he will be warned by the blinking icon.

![Screenshot](../img/feat-item-23.png)

Click to open the Suggestion view and click the tab `Change proposals`

![Screenshot](../img/feat-item-24.png)

This shows all on-going change proposals that are still pending.
Click the icon to open the details about the change proposal.

The dialog-box shows the current values in the fields for the Item, and the proposed one.
The Manager can `Approve` or `Reject` using the buttons.

![Screenshot](../img/feat-item-25.png)

Notice that the Manager can decide the fields to be updated. Meaning that the user may propose a change on fieds `Login` and `Email`, and the Manager can only accept the `Login` change.
To do so, click on the Green tick to cancel the field change.

![Screenshot](../img/feat-item-26.png)

All changes are logged into the Item history.