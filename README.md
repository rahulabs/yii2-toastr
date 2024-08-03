Yii2 - Javascript Toast Notifications
=====================================

Simple javascript toast notifications - Javascript library for non-blocking notifications. jQuery is required. The goal is to create a simple core library that can be customized and extended.

[![Latest Stable Version](https://poser.pugx.org/rahulabs/yii2-toastr/v/stable)](https://packagist.org/packages/rahulabs/yii2-toastr) [![Total Downloads](https://poser.pugx.org/rahulabs/yii2-toastr/downloads)](https://packagist.org/packages/rahulabs/yii2-toastr) [![Latest Unstable Version](https://poser.pugx.org/rahulabs/yii2-toastr/v/unstable)](https://packagist.org/packages/rahulabs/yii2-toastr) [![License](https://poser.pugx.org/rahulabs/yii2-toastr/license)](https://packagist.org/packages/rahulabs/yii2-toastr)

Installation
---------
The extension is installed using Composer installation instructions [Composer](http://getcomposer.org/doc/00-intro.md#installation-nix)

The extension is installed using Composer installation instructions
```
composer require --prefer-dist rahulabs/yii2-toastr
```
or (master)
```
composer require --prefer-dist rahulabs/yii2-toastr "dev-master"
```
or make changes to the section `require` в `composer.json` and execute `composer update`
```
"rahulabs/yii2-toastr": "^2.0"
```
or (master)

```
"rahulabs/yii2-toastr": "dev-master"
```


```php
use rahulabs\widgets\toastr\Notification;

Notification::widget([
    'type' => 'info',
    'title' => 'Toast Notifications',
    'message' => 'Simple javascript toast notifications'
]);

Notification::widget([
    'type' => 'error',
    'title' => 'Toast Notifications',
    'message' => 'Simple javascript toast notifications'
]);

Notification::widget([
    'type' => 'success',
    'title' => 'Toast Notifications',
    'message' => 'Simple javascript toast notifications'
]);

Notification::widget([
    'type' => 'warning',
    'title' => 'Toast Notifications',
    'message' => 'Simple javascript toast notifications'
]);

Notification::widget([
    'type' => 'info',
    'message' => 'Simple javascript toast notifications'
]);

Notification::widget([
    'type' => 'error',
    'message' => 'Simple javascript toast notifications'
]);

Notification::widget([
    'type' => 'success',
    'message' => 'Simple javascript toast notifications'
]);

Notification::widget([
    'type' => 'warning',
    'message' => 'Simple javascript toast notifications'
]);
```
There is also the possibility of setting up a custom notification, according to the parameters provided by the developers.
 [Toastr by CodeSeven](https://github.com/CodeSeven/toastr)

![alt text](https://raw.githubusercontent.com/rahulabs/yii2-toastr/master/screenshot/screenshot-3.png "Notifications Notification::widget()")
```php
Notification::widget([
    'type' => Notification::TYPE_ERROR,
    'title' => 'Toast Notifications',
    'message' => 'Simple javascript toast notifications',
    'options' => [
        "closeButton" => false,
        "debug" => false,
        "newestOnTop" => false,
        "progressBar" => false,
        "positionClass" => Notification::POSITION_TOP_RIGHT,
        "preventDuplicates" => false,
        "onclick" => null,
        "showDuration" => "300",
        "hideDuration" => "1000",
        "timeOut" => "5000",
        "extendedTimeOut" => "1000",
        "showEasing" => "swing",
        "hideEasing" => "linear",
        "showMethod" => "fadeIn",
        "hideMethod" => "fadeOut"
    ]
]);
```

### Notifications NotificationFlash::widget()


The connection is made globally, for example in the project layouts.

```php
<?= \rahulabs\widgets\toastr\NotificationFlash::widget() ?>
```

There is also the possibility of setting up notifications according to the parameters provided by the developers. [Toastr by CodeSeven](https://github.com/CodeSeven/toastr)

```php
<?= \rahulabs\widgets\toastr\NotificationFlash::widget([
    'options' => [
        "closeButton" => true,
        "debug" => false,
        "newestOnTop" => false,
        "progressBar" => false,
        "positionClass" => \rahulabs\widgets\toastr\NotificationFlash::POSITION_TOP_RIGHT,
        "preventDuplicates" => false,
        "onclick" => null,
        "showDuration" => "300",
        "hideDuration" => "1000",
        "timeOut" => "5000",
        "extendedTimeOut" => "1000",
        "showEasing" => "swing",
        "hideEasing" => "linear",
        "showMethod" => "fadeIn",
        "hideMethod" => "fadeOut"
    ]
]) ?>
```

![alt text](https://raw.githubusercontent.com/rahulabs/yii2-toastr/master/screenshot/screenshot-4.png "Notifications NotificationFlash::widget()")

```php
\Yii::$app->session->setFlash('error', 'This is the message');
\Yii::$app->session->setFlash('success', 'This is the message');
\Yii::$app->session->setFlash('info', 'This is the message');
\Yii::$app->session->setFlash('warning', 'This is the message');
```

![alt text](https://raw.githubusercontent.com/rahulabs/yii2-toastr/master/screenshot/screenshot-5.png "Notifications NotificationFlash::widget()")

```php
\Yii::$app->session->setFlash('warning', ['Error 1', 'Error 2', 'Error 3']);
\Yii::$app->session->setFlash('success', ['Error 1', 'Error 2', 'Error 3']);
```

Acceptable parameters
---------------------
|Parameter|Default value|Available values|Description
|-------------|-----------|-----------|-----------|
|type|`info`|`info`, `error`, `success`, `warning`|Notification Type|
|title|---|---|Notification Title|
|message|`Simple javascript toast notifications`|---|Notification text|
|options|`[]`|[More details...](https://github.com/CodeSeven/toastr)|Additional options|

**Allowed type constants:**
```
TYPE_INFO = 'info'
TYPE_ERROR = 'error'
TYPE_SUCCESS = 'success'
TYPE_WARNING = 'warning'
```
**Available position constants:**
```
POSITION_TOP_RIGHT = 'toast-top-right';
POSITION_TOP_LEFT = 'toast-top-left';
POSITION_TOP_CENTER = 'toast-top-center';
POSITION_TOP_FULL_WIDTH = 'toast-top-full-width';

POSITION_BOTTOM_RIGHT = 'toast-bottom-right';
POSITION_BOTTOM_LEFT = 'toast-bottom-left';
POSITION_BOTTOM_CENTER = 'toast-bottom-center';
POSITION_BOTTOM_FULL_WIDTH = 'toast-bottom-full-width';
```


Demonstration
-------------
* Demo can be found at http://codeseven.github.io/toastr/demo.html

Additionally
-------------
* [Toastr by CodeSeven](https://github.com/CodeSeven/toastr)
* [Yii PHP Framework Version 2](https://github.com/yiisoft/yii2)
