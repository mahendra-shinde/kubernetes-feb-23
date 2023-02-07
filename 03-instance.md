## Container Instance

1. Instance of an Image which contains AT LEAST ONE process.
2. Every container is LINKED with Maximum ONE image.
3. How to create
	docker create
	docker run

### Demo

1. Download a base image

	docker pull ubuntu

2. Launch a container and install packages

	```text
	docker run --name c1 -it ubuntu bash
	        |    |     |   |   |     |
	        |    |     |   |   |     +---------- Command or Process for "-it" mode
	        |    |     |   |   +---------------- Image tag
	        |    |     |   +-------------------- Interactive Mode for container.
	        |    |     +------------------------ Logical Name assigned to container (Must be unqiue)
	        |    +------------------------------ Assign logical name
	        +----------------------------------- Command to launch new container (instance)
	```

3.	Install some packages.

	```bash
	apt update -y
	apt install fortune -y
	exit
	```

4.	Now, stop the container and delete it.

	```bash
	docker stop c1
	docker rm c1
	```

	> NOTE: The changes made in filesystem of container `c1` would be lost as soon as instance `c1` is deleted !

5.	Launch a new instance of `ubuntu` and check if it has `fortune` installed

	```
	docker run --name c2 -it ubuntu bash
	which fortune
	exit
	```
	> Expect an ERROR as the package is not installed !

6.	Clean up

	```
	docker stop c1 c2
	docker rm c1 c2
	```
	
