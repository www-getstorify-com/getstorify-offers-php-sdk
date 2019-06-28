# getstorify-offers-php-sdk

This is getStorify Offers PHP SDK for developers.


### Getting Started

Unzip the downloaded PHP SDK file and take the SDK directory out and put it in your project.

SDK directory name: `GetStorifyOffers`

### Create API Service Credentials

Login to your getStorify account and go to the Settings page.

Select API Service from the sidebar and click on CREATE APP button.

Fill in your website details and click the CREATE button to get your app credentials for your website.

When the credential is successfully created, click the MANAGE button to get your credentials values.

Copy the User ID, App ID and App Token. These values will be used later when you start working with the SDK.

You are now ready to use the credentials.

### Creating GS object

Lets say your project looks like the following after including the getStorify Offers PHP SDK.

```
/myproject
 |
 +-- GetStorifyOffers
 |   |
 |   +-- autoload.php
 |   |
 |   +-- GetStorifyOffers.php
 |   |
 |   +-- more files and directories
 |
 +-- index.php
```
Inside the `index.php` file include the `autoload.php` file from the GetStorifyOffers SDK directory.

```php
require_once __DIR__ . '/GetStorifyOffers/autoload.php';
```

Create the credentials constants for your UserID, AppID and AppToken.

```php
define('GETSTORIFY_API_SERVICE_AUTH_APPID', '123');
define('GETSTORIFY_API_SERVICE_AUTH_USERID', 'gs123');
define('GETSTORIFY_API_SERVICE_AUTH_APPTOKEN', 'abc123def');
```

Create object of the GetStorifyOffers class using your credentials.

```php
// create object
$GetStorifyOffersObj = new \GetStorifyOffers\GetStorifyOffers(
    GETSTORIFY_API_SERVICE_AUTH_APPID,
    GETSTORIFY_API_SERVICE_AUTH_USERID,
    GETSTORIFY_API_SERVICE_AUTH_APPTOKEN
);
```

Get authenticated and acquire the access token.

```php
$accessTokenResult = $GetStorifyOffersObj->getAccessToken();
```

On success, you will get the following response.

```JSON
{
  "status": "success",
  "code": 200,
  "success": {
    "appid": "123",
    "userid": "gs123",
    "domain": "https://example.com",
    "accesstoken": "abcdef1234567890fedcba"
  }
}
```

Use the returned `accesstoken` in the following API requests.

### License

[MIT License](https://github.com/www-getstorify-com/getstorify-offers-php-sdk/blob/master/LICENSE)