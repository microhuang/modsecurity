# modsecurity
modsecurity


* 1. 依赖
  * yum install httpd-devel
  
* 2. 编译modsecurity
  * ./configure --enable-standalone-module --disable-mlogc && make
  
* 3. 编译nginx
  * ./config --add-module=../modsecurity-2.9.0/nginx/modsecurity/ ......

* 4. 添加配置文件到nginx
  * cp modsecurity.conf-recommended /etc/nginx/
  * cp unicode.mapping /etc/nginx/
  
* 5. 配置nginx主机
  * ModSecurityEnabled on;
  * ModSecurityConfig modsecurity.conf;           #from modsecurity modsecurity.conf-recommended
  
* 6. 配置modsecurity规则
  
