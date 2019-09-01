# docker-node-app
It is a sample node application that is containerised and deployed using docker.

#### Build the image
Go to directory that has your `Dockerfile` and run the following command to build the Docker image. The `-t` lets you tag your image with a name so it's easier to find while `docker images` command:

```zsh
docker build -t <your username>/docker-node-app .
```
Your image will listed by `docker images` command:
```zsh
$ docker images

#Example
REPOSITORY                          TAG           ID            CREATED
node                                10            1934b0b038d1  5 days ago
<your username>/docker-node-app     latest        d64d3505b0d2  1 minute ago
```

#### Run the image
Run your image with the following command:
```zsh
docker run -it -d -p 9000:8080 <your username>/docker-node-app
```
`-d` flag runs application in detech mode, that means running the container in the background and `-p` flag redirects the public port `9000` to the private port `8080` inside the docker container.

if you wish to go inside the container, you can use following command:
```zsh
# Enter in the container
$ docker exec -it <container id> /bin/bash
```

To test your app, open [http://localhost:9000](http://localhost:9000) inside your browser.
