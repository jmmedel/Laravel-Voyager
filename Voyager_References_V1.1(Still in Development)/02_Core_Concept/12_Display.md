

Display options
Some additional options to display your BREAD

SUGGEST EDITS
There are also a few options that you can include to change the way your BREAD is displayed. You can add a display key to your json object and change the width of the particular field and even specify a custom ID.

{
    "display": {
        "width": "3",
        "id": "custom_id"
    }
}
The width is displayed on a 12-grid system. Setting it with a width of 3 will span 25% of the width.

The id will let you specify a custom id wrapper around your element. example:

<div id="custom_id">
    <!-- Your field element -->
</div>
The default number of textarea rows is 5. This can be changed:

{
    "display": {
        "rows": "10"
    }
}

