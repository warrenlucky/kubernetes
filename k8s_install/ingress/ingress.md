## 安装 ingress  deploy-->deploy-svc-->tls-ingree/ingress-->deploy-ingress/deploy-ingress
#### 1.修改了镜像地址，以及网络模式，选用 hostNetwork: true 网络模式（使用宿主机网络）
```
kubectl apply -f ingress-nginx.yaml
```
#### 2.使用官方提供的方式安装使用方式（如果国内没使用代理，官方提供的镜像地址拉去镜像会失败）
```
https://github.com/kubernetes/ingress-nginx/blob/master/docs/deploy/index.md
```
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/mandatory.yaml
```
#### 3.使用ingress关联servie服务
```
kubectl apply -f ingress.yaml
或者
kubectl apply -f tls-ingress.yaml
```
#### 4.windows本地测试
添加解析记录
编辑 C:\Windows\System32\drivers\etc\hosts文件
```
ip ingress-ip
127.0.0.1 www.netsarang.co.kr
127.0.0.1 sales.netsarang.com

```
