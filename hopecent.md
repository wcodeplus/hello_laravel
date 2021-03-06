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

## git 使用
- $ git config --global user.name "Your Name"           设置用户名
- $ git config --global user.email your@example.com     设置邮箱
- $ git config --global push.default simple             设置默认提交分支
- $ cd "../www/Laravel"                                 进入项目根目录
- $ git init                                            初始化git
- $ git config --global core.autocrlf true              设置换行和回车通用
- $ git add -A                                          将目录下全部文件添加到git缓存
- $ git status                                          查看此时的git状态
- $ git commit -m "第一次提交"                           第一次提交的git
- $ git log                                             查看git日志

## github 使用
- 注册和登录
- 设置 ssh key：复制 /administrator/.ssh/id_rsa.pub 里面的值
- 进入 github ssh 令牌管理页面：https://github.com/settings/keys 
- 新建一个 ssh key
- 新建一个 github 仓库：填仓库名字和描述即可，其他不变
- 提交代码到仓库：
    - $ git remote add origin git@github.com:wcodeplus/hello_laravel.git
    - $ git push -u origin master
- 检查是否提交成功

## 引入 bootstrap
- 安装 yarn：https://yarnpkg.com/en/docs/install#windows-stable
- 下载后安装，再配置一下环境变量（win10系统）
- Laravel 默认集成了 bootstrap，但是需要一定的配置
- cd /www/Larave/
- yarn install --no-bin-links
- yarn add cross-env
- 编辑 resources/sass/app.scss 文件，留下 `@import '~bootstrap/scss/bootstrap'` 这一行
- 保证 `npm run watch-poll` 一直运行，这样就会将 .scss 文件编译成 .css 文件（保存在public/css里面）
- 项目默认的跟目录是 public
- 解决静态缓存：在 webpack.mix.js 后面加上 .version() 即可，此时要求重启 `npm run watch-poll` 编译

# nginx 隐藏 index.php

打开 phpstudy 项目对应的配置文件 vhosts.conf 加上，之后重启 phpstudy

```
autoindex  on;
if (!-e $request_filename) {
    rewrite ^/(.*)$ /index.php/$1;
}
```

# 数据库迁移

- 低版本的 mysql 数据库进行 php artisan migrate 操作时会报长度限制的错
- 参考：https://www.cnblogs.com/betx/p/6544090.html

# 英文单词

- kernel：中心、核心
- artisan：工匠
- encrypt：加密
- Illuminate：阐明
- blade：刀片