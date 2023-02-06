## Container Images

1. Images are immutable.
2. Images are made up of multiple layers (Minimum : 1)
3. Images only occupy `storage space`
4. `Container` is instance of an image.
5. Single image can be used for creating Zero to Unlimited number of instances.
6. Images have globally unique ID
7. Single Image can have multiple names.
	- Short name: mysql:5.7
		Repository:  Collection of multiple versions of application image
		Tag :		 Certain version of image
	- Long (FQN): docker.io/library/mysql:5.7
		docker.io	is container registry
8. Download images
		docker pull IMAGENAME
		- For images from docker-hub (default registry), use short name
		- For images from OTHER registries, use FQN
