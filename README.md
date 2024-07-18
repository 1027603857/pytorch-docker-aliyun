# pytorch镜像
配置在conda下的pytorch镜像，自己做了一些调整。

启动命令
```
docker run -it -d -p 1234:22 -v /home/workspack:/workspace --gpus all --shm-size=8g --name pytorch 1027603857/pytorch bash
```
安装tensorflow
```
# tensorflow==2.13.0 tensorrt==8.6
docker run -it -d -p 1234:22 -v /YOUR_WORKSPACE:/workspace -v /TENSORRT:/usr/local/tensorrt --gpus all --shm-size=8g --name pytorch 1027603857/pytorch bash
```

本地构建
```
export IMAGE_TAG="TAG_NAME"
docker build -f ./Dockerfile --progress=auto -t "1027603857/pytorch:${IMAGE_TAG}" .
docker push "1027603857/pytorch:${IMAGE_TAG}"
```
