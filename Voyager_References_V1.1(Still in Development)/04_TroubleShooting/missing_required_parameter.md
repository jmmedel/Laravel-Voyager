

Missing required parameter
SUGGEST EDITS
Symptom:
You get an error page saying

Missing required parameters for [Route...]
Cause:
There are two possible causes:

You dont have a primary-key for your table
You have a primary-key but it's not called id
Solution:
As there are two causes, there are also two solutions:

Simply create a field id for the table
Tell your model about your primary-key:
protected $primaryKey = 'your_primary_key';
Please consider following Eloquents model conventions

