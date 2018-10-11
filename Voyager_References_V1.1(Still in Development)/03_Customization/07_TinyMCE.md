

TinyMCE
SUGGEST EDITS
If you want to customize TinyMCE within Voyager, you can do so by adding a additional JS file to your config.

In this file you have to define a function like

function tinymce_init_callback(editor)
{
    //...
}
Now you can control the TinyMCE instance(s) on the page.
For all possible variables and functions, please refer to the TinyMCE documentation.


