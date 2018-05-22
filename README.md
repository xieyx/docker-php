# Docker搭建PHP开发环境

## 环境配置
* openresty
* php7.1
* mongo
* tideways
* xhgui

## 初始化
安装docker-composer, 按照官网文档安装 :link:[链接](https://docs.docker.com/compose/install/), 然后执行以下命令
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
│   ├── php-fpm.conf
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
- build: 初始化用, 构建 `php` 和 `tideways` 镜像
- conf: 配置目录, 包括 `nginx.conf` `php.ini` `php-fpm.conf`
- data: 项目目录, `mongo` 用于存储 `xhgui` 收集的数据, `profile/xhgui-branch` 是 `xhgui` 根目录
- docker-compose.yml: `docker-compose` 配置文件
- logs: 日志目录, 包括:
  - `nginx` 的 `success.log` 和 `error.log`
  - `php` 的 `error.log` 和 `slow.log`
  - 业务日志也建议放在该目录下, 在nginx配置文件中配置即可
- run: 用于存储容器运行时的数据


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
