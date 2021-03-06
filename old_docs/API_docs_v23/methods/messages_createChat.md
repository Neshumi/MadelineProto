---
title: messages.createChat
description: messages.createChat parameters, return type and example
---
## Method: messages.createChat  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|users|Array of [InputUser](../types/InputUser.md) | Yes|
|title|[string](../types/string.md) | Yes|


### Return type: [messages\_StatedMessage](../types/messages_StatedMessage.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $this->bot_login($token);
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

$messages_StatedMessage = $MadelineProto->messages->createChat(['users' => [InputUser], 'title' => string, ]);
```

Or, if you're into Lua:

```
messages_StatedMessage = messages.createChat({users={InputUser}, title=string, })
```

