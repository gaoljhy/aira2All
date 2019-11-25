# aira2All



<p align="center">"<i>If you have a goal, then you will find a way to achieve it.</i>"</p>

<h4 align="center">all ready to use  Aira2 in one docker container .</h4>

<br>

<p align="center">
  <a href="https://github.com/gaoljhy/aira2All/tree/master">
    <img src="https://img.shields.io/badge/Branch-master-green.svg?longCache=true"
        alt="Branch">
  </a>
  <a href="https://github.com/gaoljhy/aira2All/pulls">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?longCache=true"
        alt="Pull Requests">
  </a>
  <a href="https://github.com/gaoljhy/aira2All/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-blue.svg?longCache=true"
        alt="License">
  </a>
</p>

<div align="center">
  <sub>Created by
  <a href="http://grj321.com">gaoljhy</a> and
  <a href="https://github.com/gaoljhy/aira2All/contributors">
    contributors
  </a>
</div>

<br>

****

## 目录

[github](https://github.com/gaoljhy/aira2All)


[dockerhub](https://hub.docker.com/r/adminhub/aira2)

## Usage

请使用实际的路径替换以下命令中的 `/DOWNLOAD_DIR` 和 `CONFIG_DIR`，他们将容器中的下载目录和配置文件目录映射到你指定的主机路径上，以便于管理下载的文件和 Aria2 的配置。



```sh
sudo docker run -d \
--name aria2 \
-p 6800:6800 \
-p 80:80 \
-p 21:8080 \
-v $(pwd)/DOWNLOAD_DIR:/data \
-v $(pwd)/CONFIG_DIR:/config \
-e SECRET=SECRET_CODE \
adminhub/aira2:latest
```


> 6800 为 `aria2` 端口
> 如果不需要浏览下载目录，则去掉 `-p 21:8080` 参数。  

> tips：请用随意的一组字符串替换 `SECRET_CODE`，在浏览器中管理 aria2 时需要用这个安全代码认证身份，以防他人恶意使用。  
> 如果设置了`SECRET`，在启动完成之后需要在页面配置相应的参数  

### 浏览

+ `http://localhost:80` 打开 web 管理界面
+ `http://localhost:21` 浏览下载目录
