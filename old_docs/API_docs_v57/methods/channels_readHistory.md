---
title: channels.readHistory
description: channels.readHistory parameters, return type and example
---
## Method: channels.readHistory  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|channel|[InputChannel](../types/InputChannel.md) | Yes|
|max\_id|[int](../types/int.md) | Yes|


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

$Bool = $MadelineProto->channels->readHistory(['channel' => InputChannel, 'max_id' => int, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - channels.readHistory
* params - {"channel":"InputChannel","max_id":"int"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/channels.readHistory`

Parameters:

channel - Json encoded InputChannel
max_id - Json encoded int


```

Or, if you're into Lua:

```
Bool = channels.readHistory({channel=InputChannel, max_id=int, })
```

