# TYPO3 PHP-CS-Fixer Rules

This package provides the [PHP Coding Standards Fixer]() [rules](https://git.typo3.org/typo3/typo3/-/blob/main/Build/php-cs-fixer/config.php) used by the [TYPO3 CMS](https://www.typo3.org) in a static method. Additionally, it provides the custom rules for LST TYPO3 projects in a static method. That's it.

This package has no dependencies, you need to install PHP-CS-Fixer on your own.

## Usage

Install the package via composer:
```shell
composer require lst/typo3-phpcsfixer-rules --dev
```

You can access the rules in your PHP-CS-Fixer configuration by calling `\LST\TYPO3PhpCsFixerRules\PhpCsFixer::getRules()`.

To access the official rules only, use `\LST\TYPO3PhpCsFixerRules\PhpCsFixer::getOfficialRules()`.


### Example config

An example `.php-cs-fixer.php` file to fix code in the folder `packages`:

```php
<?php

require_once 'vendor/lst/typo3-phpcsfixer-rules/src/PhpCsFixer.php';

$finder = PhpCsFixer\Finder::create()
    ->in('packages');

$config = new PhpCsFixer\Config();
return $config->setRules(\LST\TYPO3PhpCsFixerRules\PhpCsFixer::getRules())
    ->setRiskyAllowed(true)
    ->setFinder($finder);
```
