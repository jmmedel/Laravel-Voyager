

Thumbnails URL
Learn how to get thumbnails URL in Voyager

SUGGEST EDITS
Voyager will generate thumbnails for Image field type when you specify the additional field options (https://voyager.readme.io/docs/additional-field-options#section-image).

After you have your thumbnails generated, you may want to display the thumbnails in your view or get the thumbnail URL. In order to do that you need to add Resizable traits to your model.

PHP
 Copy
use TCG\Voyager\Traits\Resizable;

class Post extends Model
{
    use Resizable;
}
use TCG\Voyager\Traits\Resizable;

class Post extends Model
{
    use Resizable;
}
Then you can call the thumbnail function in your view or anywhere you like.

PHP
 Copy
@foreach($posts as $post)
    <img src="<span ng-non-bindable>{{Voyager::image($post->thumbnail('small'))}}</span>" />
@endforeach
@foreach($posts as $post)
    <img src="{{Voyager::image($post->thumbnail('small'))}}" />
@endforeach
Or you can specify the optional image field name (attribute), default to image

PHP
 Copy
@foreach($posts as $post)
    <img src="<span ng-non-bindable>{{Voyager::image($post->thumbnail('small', 'photo'))}}</span>" />
@endforeach
@foreach($posts as $post)
    <img src="{{Voyager::image($post->thumbnail('small', 'photo'))}}" />
@endforeach

