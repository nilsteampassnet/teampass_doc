
# Definition

`Custom Fields` is a feature that permits you to define your own fields. With the high level of customization, you  can define the exact configuration that fits your needs.

The `Custom Fields` are created inside `Custom Category` which are associated to Folders.

  As an example, consider a Folder called "Credit Cards". You may want to create a Custom Category called `Credit Cards` including 2 Custom Fields called `PIN` and `Expiration date`.
  Based on this, the 2 Custom Fields will be displayed for each Item stored in the folder `Credit Cards`.

# Administration

`Custom Fields` is a feature that needs to be enabled before being used. For this, 

* open Settings page 
* select tab `Options`
* enable option `Custom item fields enabled`

	Notice that you can create Custom Categories and Fields even if the option is not enabled. The option only impact the display of those categories.

# GUI

The GUI is made of 2 zones. 

![Screenshot](../img/feat-cusf-1.png)

The first one shows a Tree made of the Categories and the related Fields.

The second one is dedicated for Categories management (with specific actions).

# Add a new Category

Enter the label of Category and click `Add Category` button.
This new Category will be added in the Tree in alphabetic order.

# Rename and Delete

Those 2 actions are performed the same way. Do:

* select the Category (its name should be added in the text box),
* modify the label (in case of a renaming action),
* click the button corresponding to your action

	Notice that when deleting a Category, all attached Fields are deleted, as all the values in the Database related the Items.

# Move a Field

You can decide to move the Fields from one Category to another. Do:

* select the Category (its name should be added in the text box),
* select the Category target (with the drop list),
* click the button.

# Organize the Categories

You can decide to organize the Categories in a customer order. For this use the small text box in front of the label and enter a number.
The Categories will be sorted by number as primary criteria and by alphabetic as second criteria. 

# Associate a Folder with a Category

You need to relate the Category to Folders. for this,

* use the Tree
* click the icon `Associated folders`
* select the Folders you want (multiple selection is possible)
* click OK button to confirm

The Folders are now associated with the selected Category.

# Manage Fields

The Fields are managed through the bottom box.

The exact same feature described above are valid for Fields. The unique difference concerns the Field creation.

# Add a new Field

Adding a new field in a Category is performed as this:

* use the Tree
* spot the Category you want to improve
* click the icon +
* enter the label of the field
* confirm with the button

# Field data encryption

By default, the data inside the Fields are encrypted.

You may disable encryption using the key symbol in front of the field definition.

![Screenshot](../img/feat-cusf-2.png)

# Information

Notice that when creating a new sub-folder of a Folder that is associated to `Custom Fields` categories, this new folder will inherit of those categories.
