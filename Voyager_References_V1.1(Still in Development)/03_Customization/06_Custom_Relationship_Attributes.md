


Custom Relationship Attributes
SUGGEST EDITS
With Voyager 1.1 you are able to define additional attributes which you can show in a relationship.

For example a Post has an Author and you want to display the Users full-name.
To do so, we first need to define an Accessor in our User model:

public function getFullNameAttribute()
{
    return "{$this->first_name} {$this->last_name}";
}
After that we need to tell Voyager that there is an accessor we want to use:

public $additional_attributes = ['full_name'];
Now your user-model should look something like this:

<?php

class User extends \TCG\Voyager\Models\User
{
    public $additional_attributes = ['full_name'];

    public function getFullNameAttribute()
    {
        return "{$this->first_name} {$this->last_name}";
    }
}
Thats it! You can now select full_name in your Relationship.


