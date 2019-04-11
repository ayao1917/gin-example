## Gin Server

### Development Setup

1. install docker

2. Edit config file

    ```
    $ cp .env.example .env 
    ```

3. Run docker

    ```
    $ docker-compose up
    ```

### Cleanup And Rebuild

```
$ docker rm $(docker ps -a -f status=exited -q)
$ docker-compose build --pull
$ docker-compose up
```
