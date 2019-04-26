# Laravel 使用步骤

## 配置 PHP 环境
- 在 phpstudy.php.cn 下载 phpstudy 2018版本
- 安装后第一次打开，选择升级到最新版本
- 在软件**切换版本**中选择最新的`php7.2.10-nts + Nginx`
- 如果提示要安装 VC11 或 VC14，按要求安装即可

## 下载 Laravel
- 进入 phpstudy 的根路径 www
- 运行 `composer create-project laravel/laravel Laravel --prefer-dist "5.8.*"` 下载
- 这时候在 /www/ 目录下会有一个 /www/Laravel/ 文件夹，下载完成

## 配置虚拟域名
- 打开 phpstudy，选择**其他选项-站点域名管理**
- 配置一个虚拟域名，对应到 /www/Laravel/public 目录，如 la.cc
- 修改 hosts 文件，在最后一行添加 `127.0.0.1 la.cc`
- 打开浏览器，输入 la.cc 即可

## 了解 Laravel 目录结构
- 入口：    /www/Lavarel/public/index.php
- 控制器：  /www/Lavarel/app/Http/Controllers/
- 视图：    /www/Lavarel/resources/views/
- 路由：    /www/Lavarel/routes/

# 英文单词

- kernel：中心、核心
- artisan：工匠
- encrypt：加密
- Illuminate：阐明
- blade：刀片