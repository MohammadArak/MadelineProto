---
title: contacts.deleteContacts
description: contacts.deleteContacts parameters, return type and example
---
## Method: contacts.deleteContacts  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|id|Array of [InputUser](../types/InputUser.md) | Yes|


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

$Bool = $MadelineProto->contacts->deleteContacts(['id' => [InputUser], ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - contacts.deleteContacts
* params - {"id":["InputUser"]}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/contacts.deleteContacts`

Parameters:

id - Json encoded  array of InputUser


```

Or, if you're into Lua:

```
Bool = contacts.deleteContacts({id={InputUser}, })
```

