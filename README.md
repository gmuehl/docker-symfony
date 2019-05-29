# Docker Config for Symfony

I use Docker to simplify Development and have the same Hosts available on all
local Machines. Most of the existing Docker for Symfony
Configurations require Symfony to be in it's own Sub-Directory, 
but i wanted:

- Integrate Docker Configuration & Logs into the Symfony Directory Structure
- Keep the Data of the MySQL Database
- Use app_dev.php as Directory-Root

Do **not** Use this Configuration for Production 
and take care what you deploy!

## TODO:

- Install X-Debug and make it available for PHPStorm
- Fill PHPSTORM.md

### Mail under Symfony 3.x

First of all add your Credentials to *msmtprc*. It is very tricky to get 
the local Mail up and running. Make pretty sure that your local Symfony 
uses this Configuration:

``` yaml
# Swiftmailer Configuration
swiftmailer:
    transport: 'sendmail'

services:
    swiftmailer.mailer.default.transport:
        class:     Swift_SendmailTransport
        arguments: ['/usr/sbin/sendmail -t']
```

Take care that you have **not** added 

``` yaml
swiftmailer:
    spool: { type: memory }
```

in your *config.yml* because you can't override it *in config_dev.yml* - instead move 
a maybe existing spooling Configuration to *config_prod.yml*

Even if you have everything configured right it could still be possible that your
Provider refuses the mail (check msmtp.log). In most Cases it's a not allowed
From-Email-Address. So make sure your Code uses the right one or make it
configurable!
