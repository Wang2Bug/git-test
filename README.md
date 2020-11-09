# server-deployment

//linux
//安装mysql
//1.0 安装目录  /usr/bin/mysql

//2.0 下载 wget https://dev.mysql.com/get/Downloads/MySQL-5.7/mysql-5.7.24-linux-glibc2.12-x86_64.tar.gz
      如果没有wget 安装wget yum -y install wget
      
//2.1 官网下载 https://downloads.mysql.com/archives/community/

//3.0 安装 解压 tar xzvf mysql-5.7.24-linux-glibc2.12-x86_64.tar.gz
           mv mysql-5.7.24-linux-glibc2.12-x86_64 /usr/local/mysql
           mkdir /usr/local/mysql/data
           //开放权限
           chown -R mysql:mysql /usr/local/mysql
           chmod -R 755 /usr/local/mysql
           //添加用户
           

