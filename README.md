# PHP 8 development environment with PHP-FPM, Nginx and MySQL, using Docker and Docker Compose

You need to have Docker and Docker Compose installed on your server to proceed using this PHP environment.

The following three separate service containers will be used:

- An `app` service running PHP 8 FPM.
- A `mysql` service running MySQL.
- An `nginx` service that uses the `app` service to parse PHP code before serving the application to the final user.

## Running the environment

- Build the app image with the following command:

```bash
docker-compose build app
```

- When the build is finished, you can run the environment in background mode with:

```bash
docker-compose up -d
```

- To show information about the state of your active services, run:

```bash
docker-compose ps
```

You can use the `docker-compose exec` command to execute commands in the service containers, such as an `ls -l` to show detailed information about files in the application directory:

```bash
docker-compose exec app ls -l
```

- Now go to your browser and access your server’s domain name or IP address on port `8000`: `http://server_domain_or_IP:8000`. In case you are running this demo on your local machine, use `http://localhost:8000` to access the application from your browser.

- You can use the logs command to check the logs generated by your services:

```bash
docker-compose logs nginx
```

- If you want to pause your Docker Compose environment while keeping the state of all its services, run:

```bash
docker-compose pause
```

- You can then resume your services with:

```bash
docker-compose unpause
```

- To shut down your Docker Compose environment and remove all of its containers, networks, and volumes, run:

```bash
docker-compose down
```

# Vars to configure (if you want, doesn't needed)

- File **docker-compose.yaml**
    - **MYSQL SECTION:**
    - ***MYSQL_ROOT_PASSWORD:*** Password to access db
    - ***MYSQL_DATABASE:*** Name for your default db

## License
[MIT](https://choosealicense.com/licenses/mit/)