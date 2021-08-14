<h1 align="center">Termii PHP</h1>

<p align="center">
  <img alt="Github top language" src="https://img.shields.io/github/languages/top/Douglasokolaa/termiiphp?color=56BEB8">

  <img alt="License" src="https://img.shields.io/github/license/Douglasokolaa/termiiphp?color=56BEB8">

  <img alt="Github issues" src="https://img.shields.io/github/issues/Douglasokolaa/termiiphp?color=56BEB8" />

  <img alt="Github forks" src="https://img.shields.io/github/forks/Douglasokolaa/termiiphp?color=56BEB8" />

  <!-- <img alt="Github stars" src="https://img.shields.io/github/stars/Douglasokolaa/termiiphp?color=56BEB8" /> -->
</p>

<hr>

<p align="center">
  <a href="#dart-about">About</a> &#xa0; | &#xa0; 
  <a href="#white_check_mark-requirements">Requirements</a> &#xa0; | &#xa0;
  <a href="#checkered_flag-usage">Usage</a> &#xa0; | &#xa0;
  <a href="#hammer-contribution">Contribution</a> &#xa0; | &#xa0;
  <a href="#memo-license">License</a> &#xa0; | &#xa0;
  <a href="https://github.com/Douglasokolaa" target="_blank">Author</a>
</p>

<br>

## :dart: About ##

PHP Library for [Termii API](http://developer.termii.com/docs/)

## :white_check_mark: Requirements ##

Before starting :checkered_flag:, you need to have [Git](https://git-scm.com) and [PHP 7+](https://php.net/) installed.

## :checkered_flag: Usage ##

```bash
# Installation
$ composer require okolaa/termiiphp
```
#Usage

- Send sms
```php
$termii = new Termii('TERMII_SENDER_ID', 'TERMII_API_KEY');

$sent = $termii->sendMessage(
    [
        "phone_number" => $_ENV["TEST_PHONE_NUMBER"],
        "message" => "Unit Test Message"
    ]
);
```

- SendToken
```php
$termii = new Termii('TERMII_SENDER_ID', 'TERMII_API_KEY');

//Set Options
$termii->setMaxAttempts(2);
  ->setPinTimeToLive(5);
  ->SetPinLength(4);
  ->setPinType("NUMERIC");
  ->setMaxAttempts(1);

$sent = $termii->sendToken(
    [
        "phone_number" => $_ENV["TEST_PHONE_NUMBER"],
        "message" => "Your pin is < _pin_ >"
    ]
);
```

- verifyToken
```php
$termii = new Termii('TERMII_SENDER_ID', 'TERMII_API_KEY');
$response = $termii->verifyToken(
    [
        "pin_id" => "f862cb33-9dd3-42b3-b705-18200c0e800f",
        "pin" => "1234",
    ]
);
```

- InApp Token
```php
$termii = new Termii('TERMII_SENDER_ID', 'TERMII_API_KEY');
$response = $termii->InAppToken(
    [
        "phone_number" => $_ENV["TEST_PHONE_NUMBER"],
    ]
);
```

- Available Methods 
```php
$termii = new Termii('TERMII_SENDER_ID', 'TERMII_API_KEY');

$termii->sendMessage();
$termii->sendToken();
$termii->verifyToken();
$termii->InAppToken();
$termii->sendWithAutoGeneratedNumber();
$termii->getSenderIds();
$termii->getResponse();
$termii->setMaxAttempts();
$termii->setPinTimeToLive();
$termii->setPinType();
$termii->setChannel();
$termii->SetPinPlaceholder();
$termii->setMessageType();
$termii->setTokenMessageType();
$termii->SetPinLength();
$termii->setSender();
$termii->setAPIKey();
$termii->getSenderIds();
$termii->getBallance();
$termii->search();
```


## :hammer: Countribution

```bash
# fork and Clone the fork project
# Access the folder
$ cd termiiphp

# Install dependencies
$ composer Install

# Create .env and update
$ cp .ev.example .env

# Run test
$ ./vendor/phpunit/phpunit/phpunit tests

```

## :memo: License ##

This project is under license from MIT. For more details, see the [LICENSE](LICENSE.md) file.

Made with :heart: by <a href="https://github.com/Douglasokolaa" target="_blank">Douglas Okolaa</a>

&#xa0;

## Todo:

- Update Readme with Usage

<a href="#top">Back to top</a>
