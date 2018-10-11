

Null Values
Learn how to add Null Values in your BREAD

SUGGEST EDITS
You might want to save an input field into the database as a null value instead of an empty string.

Simply enough, inside the BREAD you can include the following Optional Details for the field:

{
    "null": ""
}
This will turn an empty string into a null value. However you might want to be able to add both an empty string and a null value to the database for that field. However you have to choose a replacement for the null value, but it can be anything you wish. For example, if you want a field to change a string (ex. Nothing) into a null value you could include the following Optional Details for that field:

{
    "null": "Nothing"
}
Now entering Nothing into the field will end up as a null value in the database.
