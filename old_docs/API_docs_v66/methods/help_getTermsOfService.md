---
title: help.getTermsOfService
description: help.getTermsOfService parameters, return type and example
---
## Method: help.getTermsOfService  
[Back to methods index](index.md)




### Return type: [help\_TermsOfService](../types/help_TermsOfService.md)

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

$help_TermsOfService = $MadelineProto->help->getTermsOfService();
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - help.getTermsOfService
* params - 

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/help.getTermsOfService`

Parameters:



```

Or, if you're into Lua:

```
help_TermsOfService = help.getTermsOfService({})
```

