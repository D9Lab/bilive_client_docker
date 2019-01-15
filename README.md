# bilive_client docker镜像

提供 `x64/amd64` `i386` `armv6/v7` `arm64v8` 版架构的镜像，tag后有`-lzghzr`后缀的为lzghzr分支，其余的为Vector000分支。  

## 使用方法  

### 拉取镜像  

    sudo docker pull disappear9/bilive_client  (latest为x64 alpine镜像，其他架构需要手动选择tag)
### 创建volume  

    sudo docker volume create bilivec_data
### 运行  

    sudo docker run -d -p 23333:23333 --name bilive_client -v bilivec_data:/app/options disappear9/bilive_client

## 关于更新  

DockerHub的Automated build只在有 git push动作时才会触发，所以镜像更新并不是实时的，需要我去手动触发更新。（`如果有更好的办法请发个issue，感谢`）
