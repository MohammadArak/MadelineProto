---
title: channels.editAdmin
description: channels.editAdmin parameters, return type and example
---
## Method: channels.editAdmin  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|channel|[InputChannel](../types/InputChannel.md) | Yes|
|user\_id|[InputUser](../types/InputUser.md) | Yes|
|role|[ChannelParticipantRole](../types/ChannelParticipantRole.md) | Yes|


### Return type: [Updates](../types/Updates.md)

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

$Updates = $MadelineProto->channels->editAdmin(['channel' => InputChannel, 'user_id' => InputUser, 'role' => ChannelParticipantRole, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - channels.editAdmin
* params - {"channel":"InputChannel","user_id":"InputUser","role":"ChannelParticipantRole"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/channels.editAdmin`

Parameters:

channel - Json encoded InputChannel
user_id - Json encoded InputUser
role - Json encoded ChannelParticipantRole


```

Or, if you're into Lua:

```
Updates = channels.editAdmin({channel=InputChannel, user_id=InputUser, role=ChannelParticipantRole, })
```

