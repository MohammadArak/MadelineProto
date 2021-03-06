---
title: messages.getBotCallbackAnswer
description: messages.getBotCallbackAnswer parameters, return type and example
---
## Method: messages.getBotCallbackAnswer  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|game|[Bool](../types/Bool.md) | Optional|
|peer|[InputPeer](../types/InputPeer.md) | Yes|
|msg\_id|[int](../types/int.md) | Yes|
|data|[bytes](../types/bytes.md) | Optional|


### Return type: [messages\_BotCallbackAnswer](../types/messages_BotCallbackAnswer.md)

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

$messages_BotCallbackAnswer = $MadelineProto->messages->getBotCallbackAnswer(['game' => Bool, 'peer' => InputPeer, 'msg_id' => int, 'data' => bytes, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - messages.getBotCallbackAnswer
* params - {"game":"Bool","peer":"InputPeer","msg_id":"int","data":"bytes"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.getBotCallbackAnswer`

Parameters:

game - Json encoded Bool
peer - Json encoded InputPeer
msg_id - Json encoded int
data - Json encoded bytes


```

Or, if you're into Lua:

```
messages_BotCallbackAnswer = messages.getBotCallbackAnswer({game=Bool, peer=InputPeer, msg_id=int, data=bytes, })
```

