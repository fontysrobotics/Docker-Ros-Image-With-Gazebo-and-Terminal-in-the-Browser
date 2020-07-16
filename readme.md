# roscloud

ROS docker images with browser terminal.

## Usage

```shell
docker build -t roscloud:kinetic docker/kinetic/
docker run -it -p <port>:4200 roscloud:kinetic shellinabox -t
```
Go to `localhost:<port>` in a browser, login with username `user` and password `7355608`. Then you will be able to run ROS commands in your browser.

## Misc
This project uses shellinabox/shellinabox and osrf/gzweb .
