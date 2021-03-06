---
title: messages.setBotCallbackAnswer
description: messages.setBotCallbackAnswer parameters, return type and example
---
## Method: messages.setBotCallbackAnswer  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|alert|[Bool](../types/Bool.md) | Optional|
|query\_id|[long](../types/long.md) | Yes|
|message|[string](../types/string.md) | Optional|
|url|[string](../types/string.md) | Optional|


### Return type: [Bool](../types/Bool.md)

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

$Bool = $MadelineProto->messages->setBotCallbackAnswer(['alert' => Bool, 'query_id' => long, 'message' => string, 'url' => string, ]);
```

Or, if you're into Lua:

```
Bool = messages.setBotCallbackAnswer({alert=Bool, query_id=long, message=string, url=string, })
```

