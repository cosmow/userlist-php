# Userlist PHP [![Build Status](https://travis-ci.com/userlist/userlist-php.svg?branch=master)](https://travis-ci.com/userlist/userlist-php)

This library helps with integrating Userlist into PHP applications.

## Installation

This library can be installed via [Composer](https://getcomposer.org):

```bash
composer require userlist/userlist dev-master
```

## Configuration

The only required configuration is the Push API key. You can get your Push API key via the [Push API settings](https://app.userlist.com/settings/push) in your Userlist account.

Configuration values can be set when creating a new push client or via environment variables. The environment takes precedence over values provided during the initialization process.

**Configuration via environment variables**

```bash
USERLIST_PUSH_KEY=401e5c498be718c0a38b7da7f1ce5b409c56132a49246c435ee296e07bf2be39
```

**Configuration during initialization**

```php
$userlist = new \Userlist\Push(['push_key' => '401e5c498be718c0a38b7da7f1ce5b409c56132a49246c435ee296e07bf2be39']);
```

## Usage

Before tracking user or event data, create a new push client. If you configured your push key via environment variables there's nothing to add. Otherwise, see the example above.

```php
$userlist = new \Userlist\Push();
```

### Tracking Users

```php
$userlist->user([
    'identifier' => 'user-1',
    'email' => 'user@example.com',
    'properties' => [
        'first_name' => 'Jane',
        'last_name' => 'Doe'
    ]
]);
```

### Tracking Events

```php
$userlist = new \Userlist\Push();
$userlist->event([
    'name' => 'project_created',
    'user' => 'user-1',
    'properties' => [
        'name' => 'Example Project',
    ]
]);
```

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/userlist/userlist-php. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The library is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Userlist project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/userlist/userlist-php/blob/master/CODE_OF_CONDUCT.md).

## What is Userlist?

[![Userlist](https://userlist.com/images/external/userlist-logo-github.svg)](https://userlist.com/)

[Userlist](https://userlist.com/) allows you to onboard and engage your SaaS users with targeted behavior-based campaigns using email or in-app messages.

Userlist was started in 2017 as an alternative to bulky enterprise messaging tools. We believe that running SaaS products should be more enjoyable. Learn more [about us](https://userlist.com/about-us/).
