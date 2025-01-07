Brevo Notifier
==============

Provides [Brevo](https://brevo.com) integration for Symfony Notifier.
This bridge was created following the rebranding of Sendinblue.

DSN example
-----------

```
BREVO_DSN=brevo://API_KEY@default?sender=SENDER
```

where:
- `API_KEY` is your api key from your Brevo account
- `SENDER` is your sender's phone number

Adding Options to a Message
---------------------------

With a Brevo Message, you can use the `BrevoOptions` class to add message options.

```php
use Symfony\Component\Notifier\Message\SmsMessage;
use Symfony\Component\Notifier\Bridge\Brevo\BrevoOptions;


$sms = new SmsMessage('+1411111111', 'My message');

// Create a custom Options
$options = new BrevoOptions([
  'webUrl' => 'webhook_url,
  'tag' => 'tag,
  'type' => 'transactional'
]);

// Add the custom options to the sms message and send the message
$sms->options($options);

$texter->send($sms);
```

See more info at https://developers.brevo.com/reference/sendtransacsms

Resources
---------

 * [Contributing](https://symfony.com/doc/current/contributing/index.html)
 * [Report issues](https://github.com/symfony/symfony/issues) and
   [send Pull Requests](https://github.com/symfony/symfony/pulls)
   in the [main Symfony repository](https://github.com/symfony/symfony)
