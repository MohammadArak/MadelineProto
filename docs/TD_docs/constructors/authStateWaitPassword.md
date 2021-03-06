---
title: authStateWaitPassword
description: User is authorized but he needs to enter its password to begin to use application
---
## Constructor: authStateWaitPassword  
[Back to constructors index](index.md)



User is authorized but he needs to enter its password to begin to use application

### Attributes:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|password\_hint|[string](../types/string.md) | Yes|Hint on password, can be empty|
|has\_recovery\_email|[Bool](../types/Bool.md) | Yes|Is recovery email set up|
|recovery\_email\_pattern|[string](../types/string.md) | Yes|Pattern of email to which recovery mail was sent, empty before recovery email was sent|



### Type: [AuthState](../types/AuthState.md)


### Example:

```
$authStateWaitPassword = ['_' => 'authStateWaitPassword', 'password_hint' => string, 'has_recovery_email' => Bool, 'recovery_email_pattern' => string, ];
```  

[PWRTelegram](https://pwrtelegram.xyz) json-encoded version:

```
{"_":"authStateWaitPassword","password_hint":"string","has_recovery_email":"Bool","recovery_email_pattern":"string"}
```


Or, if you're into Lua:  


```
authStateWaitPassword={_='authStateWaitPassword', password_hint=string, has_recovery_email=Bool, recovery_email_pattern=string, }

```


