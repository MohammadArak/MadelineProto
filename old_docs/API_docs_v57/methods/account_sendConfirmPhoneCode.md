---
title: account.sendConfirmPhoneCode
description: account.sendConfirmPhoneCode parameters, return type and example
---
## Method: account.sendConfirmPhoneCode  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|allow\_flashcall|[Bool](../types/Bool.md) | Optional|
|hash|[string](../types/string.md) | Yes|
|current\_number|[Bool](../types/Bool.md) | Optional|


### Return type: [auth\_SentCode](../types/auth_SentCode.md)

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

$auth_SentCode = $MadelineProto->account->sendConfirmPhoneCode(['allow_flashcall' => Bool, 'hash' => string, 'current_number' => Bool, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - account.sendConfirmPhoneCode
* params - {"allow_flashcall":"Bool","hash":"string","current_number":"Bool"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/account.sendConfirmPhoneCode`

Parameters:

allow_flashcall - Json encoded Bool
hash - Json encoded string
current_number - Json encoded Bool


```

Or, if you're into Lua:

```
auth_SentCode = account.sendConfirmPhoneCode({allow_flashcall=Bool, hash=string, current_number=Bool, })
```

