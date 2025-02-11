# PHP Client for Tailscale API.

## Development is suspended.

Development of the Tailscale API Client is temporarily suspended due to the service being unavailable.

([Tailscale ToS #13](https://tailscale.com/terms))


## Installation
Install with Composer:

```bash
composer require php-client/tailscale
```


## Usage

Simple example:

```php
use PhpClient\Tailscale\Tailscale;

$tailscale = new Tailscale(
    token: 'YOUR_API_TOKEN',
);  

$response = $tailscale->api->devices()->listTailnetDevices(
    tailnet: '-', // Default tailnet
);

foreach ($response->json('devices') as $device) {
    echo $device['name'];
}
```

TODO: Add more examples


## License

This package is released under the [MIT License](LICENSE.md).
