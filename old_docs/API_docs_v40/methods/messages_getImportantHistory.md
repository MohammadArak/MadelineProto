---
title: messages.getImportantHistory
description: messages.getImportantHistory parameters, return type and example
---
## Method: messages.getImportantHistory  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|peer|[InputPeer](../types/InputPeer.md) | Yes|
|max\_id|[int](../types/int.md) | Yes|
|min\_id|[int](../types/int.md) | Yes|
|limit|[int](../types/int.md) | Yes|


### Return type: [messages\_Messages](../types/messages_Messages.md)

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

$messages_Messages = $MadelineProto->messages->getImportantHistory(['peer' => InputPeer, 'max_id' => int, 'min_id' => int, 'limit' => int, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - messages.getImportantHistory
* params - {"peer":"InputPeer","max_id":"int","min_id":"int","limit":"int"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.getImportantHistory`

Parameters:

peer - Json encoded InputPeer
max_id - Json encoded int
min_id - Json encoded int
limit - Json encoded int


```

Or, if you're into Lua:

```
messages_Messages = messages.getImportantHistory({peer=InputPeer, max_id=int, min_id=int, limit=int, })
```

