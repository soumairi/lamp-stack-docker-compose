## PHP 5.4 + MySQL + PHPMyAdmin using Docker Compose

### Pre-requisites

- Docker running on the host machine.
- Docker compose running on the host machine.
- Basic knowledge of Docker.

### Run

Clone the repo

    ```bash
    git clone https://github.com/soumairi/lamp-stack-docker-compose.git
    ```

Change directory

    ```bash
    cd lamp-stack-docker-compose
    ```

Build and run the Docker containers

    ```bash
    docker-compose up -d
    ```

This builds the containers and runs them in the background, while this

    ```bash
    docker-compose up
    ```

builds the containers to outputs their logs to the console.


### Notes
- We use port-forwarding to connect to the inside of containers from our local machine.
        - webserver: http://localhost:8100
        - db: mysql://devuser:devpass@localhost:9906/dev_db
        - phpmyadmin : http://localhost:3011 (username:devuser/password:devpass)
- Our local directory, ./php, is mounted inside of the webserver container as /var/www/html/
    - The files within in our local folder will be served when we access the website inside of the container

To stop the containers run `docker-compose kill`, and to remove them run `docker-compose rm`