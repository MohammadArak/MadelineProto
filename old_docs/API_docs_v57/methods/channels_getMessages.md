---
title: channels.getMessages
description: channels.getMessages parameters, return type and example
---
## Method: channels.getMessages  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|channel|[InputChannel](../types/InputChannel.md) | Yes|
|id|Array of [int](../types/int.md) | Yes|


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

$messages_Messages = $MadelineProto->channels->getMessages(['channel' => InputChannel, 'id' => [int], ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - channels.getMessages
* params - {"channel":"InputChannel","id":["int"]}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/channels.getMessages`

Parameters:

channel - Json encoded InputChannel
id - Json encoded  array of int


```

Or, if you're into Lua:

```
messages_Messages = channels.getMessages({channel=InputChannel, id={int}, })
```

