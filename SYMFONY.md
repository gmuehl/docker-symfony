# Symfony Code Quality

There are three major ways to make your Symfony Code better, namely

- PHP Code Sniffer
- PHPStan
- PHPUnit

## PHP Code Sniffer in PhpStorm

First of all install a local Version of PHP Code Sniffer as Dev-Dependency and add a Symfony Ruleset

```
composer require squizlabs/php_codesniffer --dev
composer require escapestudios/symfony2-coding-standard:3.x-dev --dev
```

After the Installation add the new Coding Standard to Code Sniffer:

```
vendor\bin\phpcs --config-set installed_paths vendor\escapestudios\symfony2-coding-standard
vendor\bin\phpcs -i
```

If anything went right Symfony should be in the list of installed Standards.
Now you could at phpcs as Script to your *compser.json*

```
"scripts": {
    "phpcs": "vendor\\bin\\phpcs --standard=SYMFONY",
}
```

First of all tell PhpStorm that PHP Code Sniffer exist! Go to the following Section
of Settings:

```
Settings
Languages & Frameworks
PHP
Quality Tools
```

Expand the Code Sniffer area and click ... next to the Configuration list. The Code Sniffer
should allready be there as "Local".

So far this all does nothing, except you start the Inspection in a terminal. To use it in PhpStorm
we must configure a new Inspection:

Open the Settins and go to the Inspections:

```
Settings
Editor
Inspections
```

In the Tree on the Left side press **PHP | Quality Tools** and check *PHP Code Sniffer Validation*

After enabling Code Sniffer you can edit the Settings on the Right. First of all add the Symfony
Coding Standards to the "Installed Standard Paths", it should be something like

```
vendor\escapestudios\symfony2-coding-standard\Symfony
```

After that press the *Reload Button* right behind the *Coding Standards*

Symfony should appear now in the List of Coding Standards. Choose it, press the Apply Button
and you are all done.

Further Reference: https://www.jetbrains.com/help/phpstorm/using-php-code-sniffer.html

## PHPStan in PhpStorm

TODO

## PHPUnit in PHPStorm

TODO
