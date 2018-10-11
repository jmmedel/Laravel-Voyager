

Installation
Learn how to install Voyager

SUGGEST EDITS
Voyager is super easy to install. After creating your new Laravel application you can include the Voyager package with the following command:

Shell
 Copy
$ composer require tcg/voyager
$ composer require tcg/voyager
Next make sure to create a new database and add your database credentials to your .env file, you will also want to add your application URL in the APP_URL variable:

.env
 Copy
APP_URL=http://localhost
DB_HOST=localhost
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
APP_URL=http://localhost
DB_HOST=localhost
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
Using Laravel 5.4?
If you are installing with Laravel 5.4 you will need to add the Service Provider manually. Otherwise, if you are on 5.5 this happens automatically thanks to package auto-discovery.

Finally, we can install Voyager. You can choose to install Voyager with dummy data or without the dummy data. The dummy data will include 1 admin account (if no users already exist), 1 demo page, 4 demo posts, 2 categories and 7 settings.

To install Voyager without dummy data simply run

Shell
 Copy
php artisan voyager:install
php artisan voyager:install
If you prefer installing it with the dummy data run the following command:

Shell
 Copy
php artisan voyager:install --with-dummy
php artisan voyager:install --with-dummy
Troubleshooting
Specified key was too long error. If you see this error message you have an outdated version of MySQL, use the following solution: https://laravel-news.com/laravel-5-4-key-too-long-error

And we're all good to go!

Start up a local development server with php artisan serve And, visit the URL http://localhost:8000/admin in your browser.

If you installed with the dummy data, a user has been created for you with the following login credentials:

email: admin@admin.com
password: password

Quick note
A dummy user is only created if there are no current users in your database.

If you did not go with the dummy user, you may wish to assign admin priveleges to an existing user.
This can easily be done by running this command:

Shell
 Copy
php artisan voyager:admin your@email.com
php artisan voyager:admin your@email.com
If you wish to create a new admin user you can pass the --create flag, like so:

Shell
 Copy
php artisan voyager:admin your@email.com --create
php artisan voyager:admin your@email.com --create
And you will be prompted for the users name and password.
