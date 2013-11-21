dockerfile-app-laravel
================

Docker Container for a laravel nginx vhost, an extension of
https://github.com/outrunthewolf/dockerfile-base-nginx

### Requiries

Docker >= 0.6.x

### Usage

Clone, pull or download the repository. At the same level as the dockerfile build your container with whatever name you'd like:

```shell
sudo docker build -t app/laravel .
```

Once you've got a completed image, you can run the container outright and pipe in your local laravel files:

#### Daemon
```shell
# Daemon
sudo docker run -d -v /home/user/laravel-app app/laravel:/home/laravel/public_html app/laravel
```

#### Interactive
```shell
sudo docker run -i -t -v /home/user/laravel-app app/laravel:/home/laravel/public_html base/nginx /bin/bash
```

#### Dockerfile
Or you can couple the built container as a base for another application within its Dockerfile

```shell
# Dockerfile example

# Set the new application to inherit this container
FROM app/laravel
...
```
