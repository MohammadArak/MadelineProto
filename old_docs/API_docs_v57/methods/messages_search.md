---
title: messages.search
description: messages.search parameters, return type and example
---
## Method: messages.search  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|peer|[InputPeer](../types/InputPeer.md) | Yes|
|q|[string](../types/string.md) | Yes|
|filter|[MessagesFilter](../types/MessagesFilter.md) | Yes|
|min\_date|[int](../types/int.md) | Yes|
|max\_date|[int](../types/int.md) | Yes|
|offset|[int](../types/int.md) | Yes|
|max\_id|[int](../types/int.md) | Yes|
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

$messages_Messages = $MadelineProto->messages->search(['peer' => InputPeer, 'q' => string, 'filter' => MessagesFilter, 'min_date' => int, 'max_date' => int, 'offset' => int, 'max_id' => int, 'limit' => int, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - messages.search
* params - {"peer":"InputPeer","q":"string","filter":"MessagesFilter","min_date":"int","max_date":"int","offset":"int","max_id":"int","limit":"int"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.search`

Parameters:

peer - Json encoded InputPeer
q - Json encoded string
filter - Json encoded MessagesFilter
min_date - Json encoded int
max_date - Json encoded int
offset - Json encoded int
max_id - Json encoded int
limit - Json encoded int


```

Or, if you're into Lua:

```
messages_Messages = messages.search({peer=InputPeer, q=string, filter=MessagesFilter, min_date=int, max_date=int, offset=int, max_id=int, limit=int, })
```

