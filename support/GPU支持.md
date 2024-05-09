# container-toolkit
PS: 需要先安装Nvidia驱动
参考链接： https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html
```配置包仓库
curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \
  && curl -s -L https://nvidia.github.io/libnvidia-container/stable/deb/nvidia-container-toolkit.list | \
    sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
    sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
```
```安装依赖包
sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
```

参考链接： https://github.com/NVIDIA/k8s-device-plugin#prerequisites
``` 
kubectl create -f nvidia-device-plugin.yml
```

# 部署kuboard
```
docker run -d --restart=unless-stopped --name=kuboard -p 80:80/tcp -p 10081:10081/tcp -e KUBOARD_ENDPOINT="http://10.105.21.28:80" -e KUBOARD_AGENT_SERVER_TCP_PORT="10081" eipwork/kuboard:v3
```