# Broadcastt

Realtime web applications are the future. [Broadcastt](https://broadcastt.xyz/) provides tools to help developers create realtime applications.

## PHP HTTP Library

> Be aware that this library is still in beta and not reached the first MAJOR version.
> 
> Semantic Versioning 2.0.0
>
> Major version zero (0.y.z) is for initial development. Anything may change at any time. The public API should not be considered stable.

This library is compatible with PHP 5.4+

This is an HTTP for Laravel library. If you are looking for a client library or a different server library please check out our [list of libraries](https://broadcastt.xyz/docs/libraries).

For tutorials and more in-depth documentation, visit our [official site](https://broadcastt.xyz/).

## Documentation

### First steps

Require this package, with [Composer](https://getcomposer.org/)

```
composer require nergal/broadcastt-php-http
```

### Configuration

```php
$appId = 'YOUR_APP_ID';
$appKey = 'YOUR_APP_KEY';
$appSecret = 'YOUR_APP_SECRET';
$appCluster = 'YOUR_APP_CLUSTER';

$broadcaster = new Broadcastt\Broadcastt( $appId, $appKey, $appSecret, $appCluster) );
```


#### `appId` (Integer)

The id of the application

#### `appKey` (String)

The key of the application

#### `appSecret` (String)

The secret of the application

#### `appCluster` (String) Optional

The cluster of the application

Default value: `eu`

### Modifiers

These values can be modified with setters.

#### `debug` (Boolean)

Turns on debugging for all requests

Default value: `false`

#### `basePath` (String)

The base of the path what the request will call

Default value: `/apps/{AppId}`

#### `scheme` (String)

E.g. http or https

Default value: `http`

#### `host` (String)

The host e.g. cluster.broadcasttapp.com. No trailing forward slash

Default value: `eu.broadcasttapp.xyz` If the cluster is not set during initialization

#### `port` (String)

The http port

Default value: `80`

#### `timeout` (String)

The http timeout

Default value: `30`

#### `curlOptions` (Mixed[])

Options for the curl instance

Default value: `[]`

### Helpers

These are methods which help you modify the instance

#### `useCluster($cluster)`

Modifies the `host` value for given `cluster`

#### `encrypted()`

Short way to change `scheme` to `https` and `port` to `443`

### Usage

#### `event($channels, $name, $data, $socketId = null, $jsonEncoded = false)`

Trigger an event by providing event name and payload.

Optionally provide a socket ID to exclude a client (most likely the sender).

#### `eventBatch($batch = [], $encoded = false)`

Trigger multiple events at the same time.

#### `get($path, $params = [])`

GET arbitrary REST API resource using a synchronous http client.

All request signing is handled automatically.

## Contributing

We welcome everyone who would help us to make this library "Harder, Better, Faster, Stronger".