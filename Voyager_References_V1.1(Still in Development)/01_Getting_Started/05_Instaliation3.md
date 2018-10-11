

Adding the Service Provider
SUGGEST EDITS
This is only required if you are using Laravel 5.4!
If you are on Laravel 5.5+ you can skip this step.

To add the Voyager Service Provider open up your application config/app.php file and add TCG\Voyager\VoyagerServiceProvider::class, in the providers array like so:

config/app.php
 Copy
<?php

'providers' => [
    // Laravel Framework Service Providers...
    //...
    
    // Package Service Providers
    TCG\Voyager\VoyagerServiceProvider::class,
    // ...
    
    // Application Service Providers
    // ...
],
<?php

'providers' => [
    // Laravel Framework Service Providers...
    //...
    
    // Package Service Providers
    TCG\Voyager\VoyagerServiceProvider::class,
    // ...
    
    // Application Service Providers
    // ...
],


