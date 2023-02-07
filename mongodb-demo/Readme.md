# Mongo DB Docker Image with Default Databases and Collections

1. Build the image

	```
	docker build -t mydata . 
	docker images mydata
	```

1.	Create and start new container instance

	```
	docker run --name m1 -t -p 27017:27017 mydata
	```

1.	Use any CLient tool (like Compass) to connect using

	```yaml
	Server:	localhost:27017
	User: sa
	Password: pass12345
	```
