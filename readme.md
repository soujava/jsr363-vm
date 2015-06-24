Description
===========
This is a minimal Ubuntu base image modified for Docker-friendliness.
This box is used for running and testing JSR-363 with latest OpenJDK 9 build.

#Create

Create the vm
-------------
```
$ docker build -t soujava/jsr363vm .
```

Save
-----
Save the build to a image so you can re-run it after

```
$ sudo docker run -it --name jsr363vm soujava/jsr363vm /bin/bash
```

Check Java
------------
To check if the correct java version have been installed, run the following command

```
$ sudo docker run -it --name jsr363vm soujava/jsr363vm java -version
```

Output
-------

```
openjdk version "1.9.0-internal"
OpenJDK Runtime Environment (build 1.9.0-internal-_2015_06_04_06_46-b00)
OpenJDK 64-Bit Server VM (build 1.9.0-internal-_2015_06_04_06_46-b00, mixed mode)
```

#Running Tests
This commands will run all the tests for the API

Execute unit-ri tests
----------------------

```
$ sudo docker run -it --name jsr363vm soujava/jsr363vm cd ~/unit-ri && mvn test
```

Execute unit-api tests
-----------------------

```
$ sudo docker run -it --name jsr363vm soujava/jsr363vm cd ~/unit-api && mvn test
```
