下载PHP源码
wget https://mirrors.sohu.com/php/php-7.4.15.tar.gz
解压源码
tar -xf php-7.4.15.tar.gz
安装依赖环境
apt update
apt install -y gcc g++ autoconf make openssl curl libbz2-dev pkg-config libxml2-dev libzip-dev libjpeg-dev libpng-dev libfreetype6-dev libssl-dev libsqlite3-dev libcurl4-openssl-dev libonig-dev
编译安装，并指定安装位置
cd php-7.4.15
./configure --prefix=/www/server/php74 --with-openssl --enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data --with-pdo-mysql --with-openssl --with-zlib --enable-bcmath --with-curl --enable-pcntl --with-pear --enable-sockets --enable-mbstring --enable-zip
make
make install
----
修改/server/php74/lib/php.ini配置文件
cgi.fix_pathinfo=0
----
安装常用扩展
pecl install redis 
pecl install swoole
