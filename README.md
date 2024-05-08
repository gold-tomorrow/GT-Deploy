# GT系列本地知识库系统
 - 模型服务：https://github.com/gold-tomorrow/GT-Model
 - 后端接口：https://github.com/gold-tomorrow/GT-Backend
 - 前端界面：https://github.com/gold-tomorrow/GT-Frontend
 - 系统部署：https://github.com/gold-tomorrow/GT-Deploy

# 项目介绍
本项目为系统部署项目，负责部署整套系统。

## k8s部署
k8s使用kubectl的原生yaml文件部署
```
kubectl create namespace gt
kubectl apply -f k8s/
```
## docker部署
docker需要使用较新的版本（带docker compose命令），否则需要额外安装docker-compose
```
cd docker
docker compose up -d
```
