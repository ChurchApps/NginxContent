# Docker Nginx Image

Image is configured to work as web server that serves static files. It is used in combination with rest of the [docker images](https://github.com/LiveChurchSolutions/Docker) of LCS project.

> 3402 is exposed port 

To use this image, execute following command

```sh
docker run -it -p 3402:3402 livecs/nginxcontent
```

with docker-compose:

```yml
content:
    container_name: "fs-content"
    tty: true
    image: livecs/nginxcontent
    ports:
    - "3402:3402"
    volumes:
    - content:/content
```

## Developing 
Now if you are looking to make changes to image and want to test and create container with your updated image, you can build and run container locally with these commands

```sh
docker build -t image_name:image_version .
docker run -it -p PORT:PORT image_name:image_version
```