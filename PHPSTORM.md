# Docker & Symfony in PhpStorm

Short Hints how to configure Docker in PhpStorm and run the Symfony console 
within a Container. In most Cases PhpStorm finds Docker
by itself, but in some cases you must configure it manually.

## Enable Docker Support in PhpStorm

First of all disable TLS in Docker if you are working on Windows 10! 
(Source: https://forums.docker.com/t/spotify-docker-maven-plugin-cant-connect-to-localhost-2375/9093/15).
Press the Whale Icon in the Tray and go to Settings. On the first page (General)
check the last Box: Expose daemon without TLS. Docker will restart after that.

In PhpStorm go to

```
Settings/Preferences
Build, Execution, Deployment
Docker
```

Press on Tools and make sure your binaries are working! After that go back to 
Docker itself and press the Plus Button. PhpStorm tests the Connection which
should work now. You should have a new Docker Tab now in your IDE! If you don't see
it go to

```
View
Tool Windows
Docker
```

## Starting the Containers

In the Main Menu click

```
Run
Edit Configurations
```

Click the Plus Button and press

```
Docker
Docker Compose
```

Give the Configuration a Name and in *Compose Files* add your **docker-compose.yml**

After pressing Apply in the Top Right your Run Configuration should appear showing
the Name you have chosen. By pressing the Play Button you can start the
Containers now. The Docker window will show up and PhpStorm will run
*docker-compose up -d* - if you wanna stop the Containers go to the Docker
Window and press the Stop Button. Just leaving PhpStorm does **not** stop
the Containers!

For further Information go to

https://www.jetbrains.com/help/phpstorm/docker.html

## Remote PHP Interpreter

For using X-Debug (and not having PHP on your local Machine) you must have defined PHP
as Remote Interpreter in PHPStorm. To achieve this go to Settings and click

```
Languages & Frameworks
PHP
```

Once there set the right PHP Version in "PHP Language Level".
Then Press **...** right after "CLI Interpreter". A new Dialog opens,
just press the Plus-Button at the upper left. A Select Button appers,
just Press "Prom Docker...". A new Dialog appers, first of all
choose "Docker Compose" and the right Service (PHP). After pressing
OK PhpStorm does some magic and the Remote Interpreter should appear.

## Using Xdebug in PhpStorm

Before you can start *Listening* in PhpStorm you have to enable Xdebug in the Settings.

```
Languages & Frameworks
PHP
Debug
```

Look at the Xdebug Section and make sure it is using Port 9000. All Checkboxes in this Section
should be checked. When debugging usually PhpStorms sends warnings tht i cn't find the
remote Scripts locally. So you habe to add a Server and Path Mappings in

```
Languages & Frameworks
PHP
Servers
```

Press the Plus Button at the upper left and add **localhost** on Port 80 as Server. 
Make sure that Xdebug is configures as Debugger and enable Path Mappings.
In the Path Mappings create a Mapping from your local Application Directory
to */var/www/symfony*.

**TODO: Check in a new Project that this is really working without the Xdebug Helper in Chrome.**

## Running Symfony Console

Best way is to open a Console Window as usual. 
The *Comand Line Tool Support* of PhpStorm will not work anymore!

To achieve this Start the Containers and Open the PphpStorm Docker Window.
At the left there is a list of all 4 Services you have started, and the
custom names they have got. Right-Click on the Custom Name for the *PHP* Container
and a
Menu will Popup - choose *exec* within this Menu. Now a Popup shows
up, just click on Create. In the input line just put **bash**.
PhpStorm will directly open a Terminal! Next time you open the Menu
you can directly click on bash.

Second way to achieve this is to open a Terminal and start **docker-compose exec php bash**.

