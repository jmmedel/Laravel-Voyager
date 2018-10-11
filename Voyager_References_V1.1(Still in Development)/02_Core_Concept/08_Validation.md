


Validation
Learn how to apply validation rules in your BREAD

SUGGEST EDITS
Inside of the Optional Details section for each row in your BREAD you can also specify validation rules with some simple JSON. Here is an example of how to add a validation rule or required and max length of 12

{
    "validation": {
        "rule": "required|max:12"
    }
}
Additionally, you may wish to add some custom error messages which can be accomplished like so:

{
    "validation": {
        "rule": "required|max:12",
        "messages": {
            "required": "This :attribute field is a must.",
            "max": "This :attribute field maximum :max."
        }
    }
}
Since v0.10.13 you can do the required and max:12 rule the following way:

{
    "validation": {
        "rules": [
            "required",
            "max:12"
        ]
    }
}
You can find a list of all available validation rules in the Laravel docs.


