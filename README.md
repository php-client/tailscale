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


## List of available API methods
- Contact preferences
  - Get|Update contacts
  - Resend verification email
- Device invites
  - List|Create device invites
  - Get|Accept|Resent|Delete device invite
- Device posture
  - List all posture integrations
  - Create|Get|Update|Delete posture integration
- Users
  - List users
  - Get|Approve|Suspend|Restore|Delete user
  - Update user role
- DNS
  - List|Set DNS nameservers
  - Get|Set DNS preferences
  - List|Set DNS search paths
  - Get|Update|Set split DNS
- Webhooks
  - List webhooks
  - Create|Get|Update|Delete|Test webhook
  - Rotate webhook secret
- Devices
  - List tailnet devices
  - Get|Delete|Authorize device
  - List|Set device routes
  - Set device name|tags
  - Update device key
  - Set device IPv4 address
  - Get device posture attributes
  - Set|Delete custom device posture attribute
- Tailnet settings
  - Get|Update tailnet settings
- Logging
  - List configuration audit logs
  - List network flow logs
  - Get log streaming status
  - Get|Set log streaming configuration
  - Disable log streaming
- Policy file
  - Get|Set policy file
  - Preview rule matches
  - Validate and test policy file
- Keys
  - List tailnet keys
  - Create|Get|Delete key
- User invites
  - List|Create user invites
  - Get|Delete|Resend user invite


## License

This package is released under the [MIT License](LICENSE.md).
