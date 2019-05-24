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
This Config is only for Development!

## TODO:

This project just started, but soon it should have

- Install NGINX
- Install PHP 7.3 with X-Debug
- Install MariaDB
- Install Postfix

### Next Step:

- Install NGINX
