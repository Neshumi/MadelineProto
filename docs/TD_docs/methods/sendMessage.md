---
title: sendMessage
description: Sends a message. Returns sent message. UpdateChatTopMessage will not be sent, so returned message should be used to update chat top message
---
## Method: sendMessage  
[Back to methods index](index.md)


Sends a message. Returns sent message. UpdateChatTopMessage will not be sent, so returned message should be used to update chat top message

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|chat\_id|[long](../types/long.md) | Yes|Chat to send message|
|reply\_to\_message\_id|[long](../types/long.md) | Yes|Identifier of a message to reply to or 0|
|disable\_notification|[Bool](../types/Bool.md) | Yes|Pass true, to disable notification about the message, doesn't works in secret chats|
|from\_background|[Bool](../types/Bool.md) | Yes|Pass true, if the message is sent from background|
|reply\_markup|[ReplyMarkup](../types/ReplyMarkup.md) | Yes|Bots only. Markup for replying to message|
|input\_message\_content|[InputMessageContent](../types/InputMessageContent.md) | Yes|Content of a message to send|


### Return type: [Message](../types/Message.md)

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

$Message = $MadelineProto->sendMessage(['chat_id' => long, 'reply_to_message_id' => long, 'disable_notification' => Bool, 'from_background' => Bool, 'reply_markup' => ReplyMarkup, 'input_message_content' => InputMessageContent, ]);
```

Or, if you're into Lua:

```
Message = sendMessage({chat_id=long, reply_to_message_id=long, disable_notification=Bool, from_background=Bool, reply_markup=ReplyMarkup, input_message_content=InputMessageContent, })
```


## Usage of reply_markup

You can provide bot API reply_markup objects here.  


