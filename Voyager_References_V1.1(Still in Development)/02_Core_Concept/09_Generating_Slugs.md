

Generating Slugs
Learn how to generate slugs in your the additional field options

SUGGEST EDITS
Using the bread builder you may wish to automatically generate slugs of a certain input. Lets say you have some posts, which have a title and a slug. If you want to automatically generate the slug from the title attribute, you may include the following Optional Details:

{
    "slugify": {
        "origin": "title", 
        "forceUpdate": true
    }
}
This will automatically generate the slug from the input of the title field. If a slug does already exists, it will only be updated if forceUpdate is set enabled, by default this is disabled.

