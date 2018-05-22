# Docker搭建PHP开发环境

## 环境配置
> openresty
> php7.1
> mongo
> tideways

## 初始化
安装docker-composer, 按照官网文档安装🔗[链接](https://docs.docker.com/compose/install/)
然后执行以下命令
```sh
$ git clone https://github.com/xieyx/docker-php.git
$ cd docker-php
$ docker-composer build
$ docker-composer up -d
```

## 目录结构
```sh
$ tree -L 2
.
├── build
│   ├── php
│   └── tideways
├── conf
│   ├── conf.d
│   ├── nginx.conf
│   └── php.ini
├── data
│   ├── mongo
│   └── profile
├── docker-compose.yml
├── logs
│   ├── nginx
│   └── php
└── run
    └── nginx.pid
```

## 使用
在项目入口添加
```php
require_once('/data/www/profile/xhgui/xhgui-branch/external/header.php');
```
然后通过浏览器访问http://xhgui.sina.com.cn

## 截图
![image](https://github.com/xieyx/docker-php/raw/master/images/1.png)
![image](https://github.com/xieyx/docker-php/raw/master/images/2.png)
![image](https://github.com/xieyx/docker-php/raw/master/images/3.png)
![image](https://github.com/xieyx/docker-php/raw/master/images/4.png)
