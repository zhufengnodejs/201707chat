# 布署服务器
## 购买阿里云服务器

## 连接服务器
```
ssh root@47.104.11.188
```

## 升级操作系统
```
apt-get update
```

## 安装 npm
```
apt-get install npm
```

## 安装一个node版本管理工具 n
```
npm install n -g
```

## 通过n安装node
```
n 7.5
```

## 安装git
```
apt-get install git
```

## 安装代码
```
git clone https://github.com/zhufengnodejs/201707chat.git
cd 201707chat
npm install
node server.js
```
访问 http://47.104.11.188

## 安装进程管理器pm2
```
npm install pm2 -g
```

## 启动服务器
```
pm2 start server.js --name "chat"
```

## 安装nginx
```
apt-get install nginx
```

## 配置nginx
```
chat.zhufengpeixun.cn
```
在
/etc/nginx/sites-enabled
目录下面创建一个文件，里面的内容
```
server {
        listen 80;
        server_name chat.zhufengpeixun.cn;

        location / {
           proxy_pass http://127.0.0.1:8080;
        }
}
```