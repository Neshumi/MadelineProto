---
title: closeChat
description: Chat is closed by the user. Many useful activities depends on chat being opened or closed.
---
## Method: closeChat  
[Back to methods index](index.md)


Chat is closed by the user. Many useful activities depends on chat being opened or closed.

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|chat\_id|[long](../types/long.md) | Yes|Chat identifier|


### Return type: [Ok](../types/Ok.md)

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

$Ok = $MadelineProto->closeChat(['chat_id' => long, ]);
```

Or, if you're into Lua:

```
Ok = closeChat({chat_id=long, })
```

