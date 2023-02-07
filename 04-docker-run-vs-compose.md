# Docker Compose

`docker compose` allows to define all the runtime parameters for container. 

## Single container

```yml
version: '3.5'	### Specify docker-compose schema version (String)

services:
  db:
    image: mahendrshinde/mysql-sample:sakila
    environment:
      - MYSQL_USER=mahendra
      - MYSQL_PASSWORD=pass@1234
      - MYSQL_DATABASE=sakila
    ports:
      - 3306
```

## Conditions

1.	Valid filenames for docker compose configuration are:

	```ini
	docker-compose.yml
	docker-compose.yaml
	compose.yml
	compose.yaml
	```

1.	docker-compose file must be created inside a "Folder" which acts as a project name.

	Lets assume, folder "job" contains a "compose file" with service named "db"
	Then the name of container would be "job-db-1"

1.	docker-compose commands:

	Command | Description | Example
	--------|-------------|----------------
	 up | Create and Start all the containers, use "-d" to hide all the logs | docker compose up -d
	 down | Stop and delete all the containers | docker compose down
	  ps | List all the containers | docker compose ps
	  exec | Execute a command or shell inside container | docker compose exec --index 1 db hostname -i
	  logs | Print all the logs from all instances of given service | docker compose logs db
	  pull | Pre-fetch all the images | docker compose pull

