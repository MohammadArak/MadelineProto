---
title: account.resetNotifySettings
description: account.resetNotifySettings parameters, return type and example
---
## Method: account.resetNotifySettings  
[Back to methods index](index.md)




### Return type: [Bool](../types/Bool.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$Bool = $MadelineProto->account->resetNotifySettings();
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - account.resetNotifySettings
* params - 

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/account.resetNotifySettings`

Parameters:



```

Or, if you're into Lua:

```
Bool = account.resetNotifySettings({})
```

