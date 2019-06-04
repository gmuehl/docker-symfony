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

# Running Symfony Console

TODO
