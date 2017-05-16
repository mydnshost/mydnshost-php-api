# mydnshost-php-api
PHP API for mydnshost.co.uk

At the moment this is a very simple library, will composerise this in future and add some kind of cli client wrapper around it.

This implements version 1.0 of the API as documented at https://api.mydnshost.co.uk/1.0/docs/

Example usage, listing domains:

```php
  require_once(dirname(__FILE__) . '/MyDNSHostAPI.php');
  $api = new MyDNSHostAPI('https://api.mydnshost.co.uk/');
  $api->setAuthUserKey('admin@example.org.uk', 'AAAAAAAA-BBBB-CCCC-DDDD-EEEEEEEEEEEE');

  $domains = $api->getDomains();
  var_dump($domains);
```

Example usage, importing zone files:
```php
  $domain = 'test.com';
  $zonedata = file_get_contents('test.com.db');

  echo 'Importing Domain: ', $domain, "\n";

  $result = $api->importZone($domain, $zonedata);
  if (isset($result['error'])) {
    echo 'Unable to import: ', $result['error'];
    if (isset($result['errorData'])) {
      echo ' :: ', $result['errorData'];
    }
    echo "\n"
    continue;
  } else {
    echo 'Success!', "\n";
  }
```
