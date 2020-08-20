# PHP - Cloudflare Stream

PHP CFStream is a PHP TUS client that makes it easy to send video files to Cloudflare Stream. 

- Simple interface that supports:
  - Upload videos
  - Get status of uploaded videos
  - Get embed code for videos
  - Set allowedOrigins for each video
  - Delete videos
- Implemented in pure PHP and CURL with the help of GuzzleHttp Client
- Tightly integrated with Cloudflare Stream
- Does not support:
  - Resume uploads

## Installation

Install the package via Composer as usual. Use the `dev-master` branch.

```
composer require dodgyprincess/php-cfstream dev-master
```


## Usage

#### Generic PHP Projects

If you are on composer-enabled projects, the following instructions should work for you. Otherwise try requiring `src/CFStream.php` directly in your project instead.

```
use dodgyprincess\CFStream\CFStream;

$cfstream = new CFStream($key, $zone, $email);

$resourceUrl = $cfstream->upload($filepath);
$cfstream->status($resourceUrl);
$cfstream->code($resourceUrl);
$cfstream->allow($resourceUrl, 'example.com, *.example.net');
$cfstream->delete($resourceUrl);
```


