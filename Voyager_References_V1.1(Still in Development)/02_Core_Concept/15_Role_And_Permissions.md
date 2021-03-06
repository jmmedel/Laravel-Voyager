


Roles and Permissions
Learn about the Voyager permissions

SUGGEST EDITS
Voyager comes with Roles and Permissions out of the box. Each User has a Role which has a set of Permissions.

Inside of the dashboard you can choose to Add, Edit, or delete the current Roles. Additionally when you click to edit a particular role you can specify the BREAD permissions.


New in version 1.0, we've changed Voyager's authorization system to be more in line with Laravel! This means that you can check for permissions in the following ways:

// via user object
$canViewPost = $user->can('read', $post);
$canViewPost = Auth::user()->can('read', $post);

// via controller
$canViewPost = $this->authorize('read', $post);
You may also choose to use the Voyager facade and pass the permission as a string:

$canBrowsePost = Voyager::can('browse_posts');
$canViewPost = Voyager::can('read_posts');
$canEditPost = Voyager::can('edit_posts');
$canAddPost = Voyager::can('add_posts');
$canDeletePost = Voyager::can('delete_posts');
The value of each check will return a boolean whether or not the user has that certain permission. However you might wish to throw a forbidden exception if the user does not have a certain permission. This can be done using the canOrFail method:

Voyager::canOrFail('browse_admin');
Out of the box there are some permissions you can use by default:

browse_admin: Whether or not the user may browse the Voyager admin panel.
browse_database: Whether or not the user may browse the Voyager database menu section.
browse_bread: Whether or not the user may browse the Voyager BREAD menu section.
browse_media: Whether or not the user may browse the Voyager media section.
browse_menu: Whether or not the user may browse the Voyager menu section.
browse_settings: Whether or not the user may browse the Voyager settings section.
read_settings: Whether or not the user can view or see a particular setting.
edit_settings: Whether or not the user can edit a particular setting.
add_settings: Whether or not the user can add a new setting.
delete_settings: Whether or not the user can delete a particular setting.
Additionally you can Generate permissions for every BREAD type you create. This will create the browse, read, edit, add and delete permission.

As an example, perhaps we are creating a new BREAD type from a products table. If we choose to Generate permissions for our products table. Our permission keys will be browse_products, read_products, edit_products, add_products and delete_products.

Notice
If a menu item is associated with any kind of BREAD, then it will check for the browse permission, for example for the Posts BREAD menu item, it will check for the browse_posts permission. If the user does not have the required permission, that menu item will be hidden.

Using Permissions in your Blade Template files
You can also check for permissions using blade syntax. Let's say for instance that you want to check if a user can browse_posts, simple enough we can use the following syntax:

@can('browse', $post)

    I can browse posts

@endcan
Or perhaps you need to run an else condition for a permission. That's simple enough:

@can('browse', $post)

    I can browse posts

@else

    I cannot browse posts

@endcan
Couldn't be easier, right ;)

