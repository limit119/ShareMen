# Laravel-admin项目搭建
1. 将`.env.example`拷贝为`.env`文件，配置好自己的数据库  
    ```php 
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=laravel_admin
    DB_USERNAME=root
    DB_PASSWORD=root
    ```
2. 生成项目秘钥`php artisan key:generate`   
3. 按照[官网文档](https://laravel-admin.org/docs/zh/1.x/installation)一步一步来
    ```
    composer require encore/laravel-admin:1.*  
    
    然后运行下面的命令来发布资源：  
    php artisan vendor:publish --provider="Encore\Admin\AdminServiceProvider" 
     
    在该命令会生成配置文件config/admin.php，可以在里面修改安装的地址、数据库连接、以及表名，建议都是用默认配置不修改。
    然后运行下面的命令完成安装：  
    php artisan admin:install
    ```
4. 访问项目  
    如果访问`http://sh.lc/admin/`报404（sh.lc是配置的虚拟域名），需要配置伪静态，根目录下`.hstccess`文件需要加上以下内容：
    ```php 
    Options +FollowSymLinks -Indexes
    RewriteEngine On
    
    RewriteCond %{HTTP:Authorization} .
    RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
    
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.php [L]
   ```   
    如果加了以上内容无效，phpstudy也要配置一下，将以上内容加到伪静态里，设置路口：  
    `网站 -> 管理 -> 修改 -> 伪静态`
# ShareMen
后台管理
2019-11-27

# 2022-04-03 开始二次开发
1. 更新插件 
> comspoer update

# 2022-05-19
Laravel-admin 项目搭建完成
