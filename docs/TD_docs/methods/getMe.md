---
title: getMe
description: Returns current logged in user
---
## Method: getMe  
[Back to methods index](index.md)


YOU CANNOT USE THIS METHOD IN MADELINEPROTO


Returns current logged in user

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|


### Return type: [User](../types/User.md)

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

$User = $MadelineProto->getMe();
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - getMe
* params - 

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/getMe`

Parameters:



```

Or, if you're into Lua:

```
User = getMe({})
```

