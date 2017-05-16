# mydnshost-php-api
PHP API for mydnshost.co.uk

At the moment this is a very simple library, will composerise this in future and add some kind of cli client wrapper around it.

This implements version 1.0 of the API as documented at https://api.mydnshost.co.uk/1.0/docs/

Example usage:

```php
  require_once(dirname(__FILE__) . '/MyDNSHostAPI.php');
  $api = new MyDNSHostAPI('https://api.mydnshost.co.uk/');
  $api->setAuthUserKey('admin@example.org.uk', 'AAAAAAAA-BBBB-CCCC-DDDD-EEEEEEEEEEEE');

  $domains = $api->getDomains();
  var_dump($domains);
```
