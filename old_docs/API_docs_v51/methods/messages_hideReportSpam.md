---
title: messages.hideReportSpam
description: messages.hideReportSpam parameters, return type and example
---
## Method: messages.hideReportSpam  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|peer|[InputPeer](../types/InputPeer.md) | Yes|


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

$Bool = $MadelineProto->messages->hideReportSpam(['peer' => InputPeer, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - messages.hideReportSpam
* params - {"peer":"InputPeer"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.hideReportSpam`

Parameters:

peer - Json encoded InputPeer


```

Or, if you're into Lua:

```
Bool = messages.hideReportSpam({peer=InputPeer, })
```

