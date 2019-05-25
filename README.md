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

- Install Postfix and make sure Symfony can send Mail
- Install X-Debug and make it available for PHPStorm

### Next Step:

- Get Symfony Running

### Resources

- https://blog.rafalmuszynski.pl/how-to-configure-docker-for-symfony-4-applications/
- https://github.com/maxpou/docker-symfony
- https://github.com/eko/docker-symfony
- https://medium.com/@romaricp/the-perfect-kit-starter-for-a-symfony-4-project-with-docker-and-php-7-2-fda447b6bca1
- https://knplabs.com/en/blog/how-to-dockerise-a-symfony-4-project
