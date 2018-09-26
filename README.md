<p align="center"><img src="https://seeklogo.com/images/S/slack-logo-DE4445077C-seeklogo.com.png" height="60px"><img src="https://laravel.com/assets/img/components/logo-laravel.svg" height="60px"></p>

<p align="center">
<a href="https://travis-ci.com/gpressutto5/laravel-slack"><img src="https://img.shields.io/travis/com/gpressutto5/laravel-slack/master.svg?style=for-the-badge" alt="Build Status"></a>
<a href="https://codecov.io/gh/gpressutto5/laravel-slack"><img src="https://img.shields.io/codecov/c/github/gpressutto5/laravel-slack/master.svg?style=for-the-badge" alt="codecov"></a>
<a href="https://packagist.org/packages/gpressutto5/laravel-slack"><img src="https://img.shields.io/packagist/v/gpressutto5/laravel-slack.svg?style=for-the-badge" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/gpressutto5/laravel-slack"><img src="https://img.shields.io/packagist/php-v/gpressutto5/laravel-slack.svg?style=for-the-badge" alt="PHP from Packagist"></a>
<a href="https://packagist.org/packages/gpressutto5/laravel-slack"><img src="https://img.shields.io/badge/laravel-%3E%3D5.5-orange.svg?style=for-the-badge" alt="Laravel Version"></a>
<a href="https://packagist.org/packages/gpressutto5/laravel-slack"><img src="https://img.shields.io/packagist/dt/gpressutto5/laravel-slack.svg?style=for-the-badge" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/gpressutto5/laravel-slack"><img src="https://img.shields.io/packagist/l/gpressutto5/laravel-slack.svg?style=for-the-badge" alt="License"></a>
<br>
Based on <a href="https://github.com/illuminate/mail">illuminate/mail</a>
</p>

## About Laravel Slack

Slack notification for Laravel as it should be.
Easy, fast, simple and **highly testable**.
Since it uses On-Demand Notifications, it requires Laravel 5.5 or higher.

## Installation 

Require this package in your composer.json and update your dependencies:

```bash
composer require tigran-cl/laravel-slack
```

Since this package supports Laravel's Package Auto-Discovery
you don't need to manually register the ServiceProvider.

After that, publish the configuration file:

```bash
php artisan vendor:publish --provider="Pressutto\LaravelSlack\ServiceProvider"
```

You're gonna need to configure an ["Incoming Webhook"](https://api.slack.com/incoming-webhooks) integration for your Slack team.

## Configuration

The motivation for this fork is to allow pointing a channel to a webhook url. Instead of having just one
SLACK_WEBHOOK_URL env variable, this package has an array in the config. Point your channel name to that channel's webhook url
like so in laravel-slack.php (the published config file) :

```php
    'slack_webhook_urls' => [
        '#channel1' => env('CHANNEL1_WEBHOOK_URL'),
        '#channel2' => env('CHANNEL2_WEBHOOK_URL')
    ]
```

So when you do \Slack::to('#channel1'), it will use the webhook URL you configured for it.

For the original package see https://github.com/gpressutto5/laravel-slack