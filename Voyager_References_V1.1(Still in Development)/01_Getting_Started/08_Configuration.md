

Configurations
Learn all about the Voyager configuration file.

SUGGEST EDITS
With the installation of Voyager you will find a new configuration file located at config/voyager.php.
In this file you can find various options to change the configuration of your Voyager installation.

Below we will take a deep dive into the configuration file and give a detailed description of each configuration set.

User
voyager.php
 Copy
<?php

'user' => [
    'add_default_role_on_register' => true,
    'default_role'                 => 'user',
    'admin_permission'             => 'browse_admin',
    'namespace'                    => App\User::class,
    'redirect'                     => '/admin'
],
<?php

'user' => [
    'add_default_role_on_register' => true,
    'default_role'                 => 'user',
    'admin_permission'             => 'browse_admin',
    'namespace'                    => App\User::class,
    'redirect'                     => '/admin'
],
add_default_role_on_register: Specify whether you would like to add the default role to any new user that is created.
default_role: You can also specify what the default_role is of the user.
admin_permission: The permission needed to view the admin dashboard.
namespace: The namespace of your apps User Class.
redirect: Redirect path after the user logged in.

Controller
voyager.php
 Copy
<?php

'controllers' => [
    'namespace' => 'TCG\\Voyager\\Http\\Controllers',
],
<?php

'controllers' => [
    'namespace' => 'TCG\\Voyager\\Http\\Controllers',
],
You can specify the default controller namespace of Voyager. If you ever wish to override any of the core functionality of Voyager you can do so by duplicating the Voyager controllers and specifying the location of your custom controllers.

Overwrite a single controller
If you only want to overwrite a single controller, you might consider adding the following piece of code to your AppServiceProvider class in the register method.

$this->app->bind(VoyagerBreadController::class, MyBreadController::class);

Model
voyager.php
 Copy
<?php

'models' => [
    //'namespace' => 'App\\',
],
<?php

'models' => [
    //'namespace' => 'App\\',
],
You can specify the namespace or location of your models. This is used when creating the Models from the database section of Voyager. If not defined the default application namespace will be used.

Asset
voyager.php
 Copy
<?php

'assets_path' => '/vendor/tcg/voyager/assets',
<?php

'assets_path' => '/vendor/tcg/voyager/assets',
You may wish to specify a different asset path. If your site lives in a subfolder you may need to include that directory to the beginning of the path. This may also be used in case you wish to duplicate the published assets and customize your own.

Note: When upgrading to new version of voyager the assets located in the /vendor/tcg/voyager/assets directory may need to be overwritten, so if you wish to customize any styles you will want to duplicate that directory and specify the new location of your asset_path.

Storage
voyager.php
 Copy
<?php

'storage' => [
    'disk' => 'public',
],
<?php

'storage' => [
    'disk' => 'public',
],
By default Voyager is going to use the public local storage. You can additionally use any driver inside of your config/filesystems.php. This means you can use S3, Google Cloud Storage, or any other file storage system you would like.

Database
voyager.php
 Copy
<?php

'database' => [
    'tables' => [
        'hidden' => ['migrations', 'data_rows', 'data_types', 'menu_items', 'password_resets', 'permission_role', 'settings'],
    ],
],
<?php

'database' => [
    'tables' => [
        'hidden' => ['migrations', 'data_rows', 'data_types', 'menu_items', 'password_resets', 'permission_role', 'settings'],
    ],
],
You may wish to hide some database tables in the Voyager database section. In the database config you can choose which tables would like to hide.

Prefix
voyager.php
 Copy
<?php

'prefix' => 'admin',
<?php

'prefix' => 'admin',
In this config you can specify an alternate prefix for visiting Voyager. Instead of visiting /admin perhaps you want to visit /backend to visit the Voyager admin.

Multilingual
voyager.php
 Copy
<?php

'multilingual' => [
    'enabled' => false,
    'default' => 'en',
    'locales' => [
        'en',
        //'pt',
    ],
],
<?php

'multilingual' => [
    'enabled' => false,
    'default' => 'en',
    'locales' => [
        'en',
        //'pt',
    ],
],
You can specify whether or not you want to enable mutliple languages. You can then specify your default language and all the support languages (locales)

Dashboard
voyager.php
 Copy
<?php

'dashboard' => [
    'navbar_items' => [
        'Profile' => [
            'route'         => 'voyager.profile',
            'classes'       => 'class-full-of-rum',
            'icon_class'    => 'voyager-person',
        ],
        'Home' => [
            'route'         => '/',
            'icon_class'    => 'voyager-home',
            'target_blank'  => true,
        ],
        'Logout' => [
            'route'      => 'voyager.logout',
            'icon_class' => 'voyager-power',
        ],
    ],
    'widgets' => [
        'TCG\\Voyager\\Widgets\\UserDimmer',
        'TCG\\Voyager\\Widgets\\PostDimmer',
        'TCG\\Voyager\\Widgets\\PageDimmer',
    ],
],
<?php

'dashboard' => [
    'navbar_items' => [
        'Profile' => [
            'route'         => 'voyager.profile',
            'classes'       => 'class-full-of-rum',
            'icon_class'    => 'voyager-person',
        ],
        'Home' => [
            'route'         => '/',
            'icon_class'    => 'voyager-home',
            'target_blank'  => true,
        ],
        'Logout' => [
            'route'      => 'voyager.logout',
            'icon_class' => 'voyager-power',
        ],
    ],
    'widgets' => [
        'TCG\\Voyager\\Widgets\\UserDimmer',
        'TCG\\Voyager\\Widgets\\PostDimmer',
        'TCG\\Voyager\\Widgets\\PageDimmer',
    ],
],
In the dashboard config you can add navbar_items, make the data_tables responsive, and manage your dashboard widgets.

navbar_items
Include a new route in the main user navbar dropdown by including a 'route', 'icon_class', and 'target_blank'.

data_tables
If you set 'responsive' to true the datatables will be responsive.

widgets
Here you can manage the widgets that live on your dashboard. You can take a look at an example widget class by viewing the current widgets inside of tcg/voyager/src/Widgets.

Primary color
voyager.php
 Copy
<?php

'primary_color' => '#22A7F0',
<?php

'primary_color' => '#22A7F0',
The default primary color for the Voyager admin dashboard is a light blue color. You can change that primary color by changing the value of this config.

Show developer tips
voyager.php
 Copy
<?php

'show_dev_tips' => true,
<?php

'show_dev_tips' => true,
In the Voyager admin there are developer tips or notifications that will show you how to reference certain values from Voyager. You can choose to hide these notifications by setting this configuration value to false.

Additional stylesheets
voyager.php
 Copy
<?php

'additional_css' => [
    //'css/custom.css',
],
<?php

'additional_css' => [
    //'css/custom.css',
],
You can add your own custom stylesheets that will be included in the Voyager admin dashboard. This means you could technically create a whole new theme for Voyager by adding your own custom stylesheet.

Additional javascript
voyager.php
 Copy
<?php

'additional_js' => [
    //'js/custom.js',
],
<?php

'additional_js' => [
    //'js/custom.js',
],
The same goes for this configuration. You can add your own javascript that will be executed in the Voyager admin dashboard. Add as many javascript files as needed.

Google Maps
voyager.php
 Copy
<?php

'googlemaps' => [
	'key'    => env('GOOGLE_MAPS_KEY', ''),
	'center' => [
	    'lat' => env('GOOGLE_MAPS_DEFAULT_CENTER_LAT', '32.715738'),
	    'lng' => env('GOOGLE_MAPS_DEFAULT_CENTER_LNG', '-117.161084'),
	],
	'zoom' => env('GOOGLE_MAPS_DEFAULT_ZOOM', 11),
],
<?php

'googlemaps' => [
	'key'    => env('GOOGLE_MAPS_KEY', ''),
	'center' => [
	    'lat' => env('GOOGLE_MAPS_DEFAULT_CENTER_LAT', '32.715738'),
	    'lng' => env('GOOGLE_MAPS_DEFAULT_CENTER_LNG', '-117.161084'),
	],
	'zoom' => env('GOOGLE_MAPS_DEFAULT_ZOOM', 11),
],
There is a new data type called coordinates that allow you to add a google map as a datatype. The user can then drag and drop a pin in the Google Maps to save a longitude and latitude value in the database.

In this config you can set the default Google Maps Keys and center location. This call also be added to your .env file.

