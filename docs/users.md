# Users

User objects, followings and followed videos.

## Functions

```$token``` is an optional parameter, but required to be set somewhere.

```php
<?php

// User object
user($user);

// Authenticated user object
authUser($token);

// Followed streams who are live
liveChannels($token);

// Videos from channels you follow
followedChannelVideos($token);

```

## Example Usage

File: ```App/Https/Controllers/UsersController.php```

```php
<?php

namespace App\Http\Controllers;

use TwitchApi
use App\Http\Controllers\Controller;

class UsersController extends Controller
{
    public function user()
    {
        return TwitchApi::user('zarlach');
    }

    public function authUser()
    {
        TwitchApi::setToken('xxxxxxxxxxxxxx');

        return TwitchApi::authUser();
    }
}
```
