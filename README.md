# modsecurity
modsecurity


* 1. 依赖
  * yum install httpd-devel
  
* 2. 编译modsecurity
  * ./configure --enable-standalone-module --disable-mlogc && make
  
* 3. 编译nginx
  * ./config --add-module=../modsecurity-2.9.0/nginx/modsecurity/ ......

* 4. 添加配置文件到nginx
  * mkdir /etc/nginx/owasp/
  * cp modsecurity.conf-recommended /etc/nginx/owasp/modsecurity.conf
  * cp unicode.mapping /etc/nginx/owasp/
  
* 5. 配置nginx主机
  * ModSecurityEnabled on;
  * ModSecurityConfig owasp/modsecurity.conf;           #基本配置  from modsecurity modsecurity.conf-recommended
  
* 6. 配置modsecurity.conf规则
```
wget https://github.com/SpiderLabs/owasp-modsecurity-crs/archive/master.zip
unzip master.zip
```
```
Include owasp-modsecurity-crs-master/modsecurity_crs_10_setup.conf         #主要规则
Include owasp-modsecurity-crs-master/base_rules/*.conf                     #基本规则
#Include owasp-modsecurity-crs-master/optional_rules/*.conf                #可选规则
```
  


https://github.com/SpiderLabs/owasp-modsecurity-crs
