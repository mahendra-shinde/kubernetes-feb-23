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
	        |    +------------------------------ Assigne logical name
	        +----------------------------------- Command to launch new container (instance) 
	```

3.	Install some packages.

	
