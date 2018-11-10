Docker image: php-xdebug
===
This image is based on the official php-cli image and install also xDebug.
The idea behind this image is a flexible php interpreter with xdebug support for your IDE. 
I know there are many php images with xDebug support, but often they also have more stuff 
included than xDebug and I want an image only with the necessary.

Note
---
This version isn't a stable version, because php version 7.3 is not released at this moment.
Current versions:
* php: 7.3.0RC5
* xDebug: 2.7.0beta1

Base image
---
* [php-cli](https://hub.docker.com/_/php/)

Extensions
---
* [xDebug](https://xdebug.org/)

Configure PhpStorm
---
### Docker Server
Go to ***Settings > Build, Execution, Deployment > Docker*** and add with the plus button a new docker server.

![docker server](https://github.com/GagaMen/php-xdebug/raw/master/Resources/Images/docker_server.png)

see also: https://confluence.jetbrains.com/display/PhpStorm/Docker+Support+in+PhpStorm

##### Engine API URL
* Windows: tcp://localhost:2375
* Mac: unix:///var/run/docker.sock
* Linux: unix:///var/run/docker.sock

### PHP Interpreter
Pull the image with your required version:

* ``docker pull gagamen/php-xdebug:latest``
* ``docker pull gagamen/php-xdebug:<php_version>``

Go to ***Settings > Language & Frameworks > PHP***, then click the "three-dot-button" behind CLI Interpreter.

![php_settings](https://github.com/GagaMen/php-xdebug/raw/master/Resources/Images/php_settings.png)

Now add a new interpreter by pressing the green plus symbol in the left top corner and choose "From Docker, Vagrant, VM, Remote, ...".

![add_interpreter](https://github.com/GagaMen/php-xdebug/raw/master/Resources/Images/add_interpreter.png)

Choose Docker in the new popup window, select your defined docker server and the previously downloaded docker image.

![choose_docker_image](https://github.com/GagaMen/php-xdebug/raw/master/Resources/Images/choose_docker_image.png)

Add for each php version, do you want to use, one interpreter and then apply the changes.

### Configure xDebug
* Install browser toolbar or bookmarklets and choose **PHPSTORM** as IDE key, which your can define in the add-on settings.
    * See also: https://confluence.jetbrains.com/display/PhpStorm/Browser+Debugging+Extensions
* Enable listening for PHP Debug Connections with the Button in the top right corner.
    * See also: ***Settings > Language & Frameworks > PHP > Debug***
* After that set a breakpoint and run your script in debug mode

