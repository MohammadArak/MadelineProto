---
title: payments.sendPaymentForm
description: payments.sendPaymentForm parameters, return type and example
---
## Method: payments.sendPaymentForm  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|msg\_id|[int](../types/int.md) | Yes|
|requested\_info\_id|[string](../types/string.md) | Optional|
|shipping\_option\_id|[string](../types/string.md) | Optional|
|credentials|[InputPaymentCredentials](../types/InputPaymentCredentials.md) | Yes|


### Return type: [payments\_PaymentResult](../types/payments_PaymentResult.md)

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

$payments_PaymentResult = $MadelineProto->payments->sendPaymentForm(['msg_id' => int, 'requested_info_id' => string, 'shipping_option_id' => string, 'credentials' => InputPaymentCredentials, ]);
```

Or, if you're using [PWRTelegram](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - payments.sendPaymentForm
* params - {"msg_id":"int","requested_info_id":"string","shipping_option_id":"string","credentials":"InputPaymentCredentials"}

```

### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/payments.sendPaymentForm`

Parameters:

msg_id - Json encoded int
requested_info_id - Json encoded string
shipping_option_id - Json encoded string
credentials - Json encoded InputPaymentCredentials


```

Or, if you're into Lua:

```
payments_PaymentResult = payments.sendPaymentForm({msg_id=int, requested_info_id=string, shipping_option_id=string, credentials=InputPaymentCredentials, })
```

