# 较laradock/laradock做的配置修改
## 1，env-example
### line 8
```php
APP_CODE_PATH_HOST=../wwwroot  //原为APP_CODE_PATH_HOST=../
```
### line 41
```php
PHP_VERSION=7.1 //原为 PHP_VERSION=7.3
```
### line 71 
```php
//修改镜像源，
CHANGE_SOURCE=true  //原为 false
```

### line 89
```php
WORKSPACE_NPM_REGISTRY=https://registry.npm.taobao.org //原为空，下载nodejs时使用否则注定失败
```

### line 133
```php
WORKSPACE_INSTALL_SWOOLE=true //原为false
```

### line 146
```php
WORKSPACE_TIMEZONE=Asia/Shanghai //原为UTC
```

### 180
```php
PHP_FPM_INSTALL_SWOOLE=true //原为false
```

### 210
```php
PHP_WORKER_INSTALL_SWOOLE=true //原为false
```

### 249
```php
MYSQL_VERSION=5.7 //原为latest
```

## php-fpm\Dockerfile

### 29 
```php
sed -i 's/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/' /etc/apt/sources.list \
//原为 sed -i 's/deb.debian.org/mirrors.aliyun.com/' /etc/apt/sources.list \
//阿里云镜像下载libpython时报错，遂换之
```