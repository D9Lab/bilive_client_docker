# bilive_client docker镜像

提供 `x64/amd64` `i386` `armv6/v7` `arm64v8` 版架构的镜像，tag后有`-lzghzr`后缀的为lzghzr分支，其余的为Vector000分支。  

## Tags

`arm`: For arm32v6 arm32v7
`arm64`: For arm64v8
`x64/latest`: For x64(Linux)
`i386`: For x32(Linux)

由于DockerHub的Autobuild系统限制，无法提供Windows版镜像。

2019/06/17 : 由于原作者的服务器挂了，现加入server镜像，tag后缀为-server的为 https://github.com/bilive/bilive_server 镜像

## 使用方法  

### 拉取镜像  

    sudo docker pull disappear9/bilive_client  (latest为x64 alpine镜像，其他架构需要手动选择tag)
### 创建volume  

    sudo docker volume create bilivec_data
### 运行  

    sudo docker run -d -p 23333:23333 --name bilive_client -v bilivec_data:/app/options disappear9/bilive_client

## 关于更新  

<del>DockerHub的Automated build只在有 git push动作时才会触发(或源镜像有更新时)，所以镜像更新并不是实时的，需要我手动去触发更新。</del>  
现在Vector000分支加入了自动更新，container每次启动时都会更新+重新编译。
（`如果有更好的办法请发个issue，感谢`）
