# Users

Video objects, top lists and channel videos.

## Functions

```$token``` is an optional parameter, but required to be set somewhere.

```php
<?php

// Video object
video($id);

// List of videos in a time period, ordered by views
videosTop($options);

// List of channel videos
options = [
    'limit' => 10,
    'offset' => 0,
    'broadcasts' => '',
    'hls' => '',
];
channelsVideo($channel, $options);

```

## Example Usage

File: ```app/Https/Controllers/VideosController.php```

```php
<?php

namespace App\Http\Controllers;

use TwitchApi;
use App\Http\Requests;
use Illuminate\Http\Request;
use App\Http\Controllers\Controller;

class VideosController extends Controller
{
    public function topList()
    {
        $options = [
            'limit' => 10,
        ];
        return TwitchApi::videosTop($options);
    }
}
```