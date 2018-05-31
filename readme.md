# Nginx
[![Build Status](https://github.com/nanqinlang/SVG/blob/master/build%20passing.svg)](https://github.com/nanqinlang/Nginx)
[![language](https://github.com/nanqinlang/SVG/blob/master/language-c-blue.svg)](https://github.com/nanqinlang/Nginx)
[![author](https://github.com/nanqinlang/SVG/blob/master/author-nanqinlang-lightgrey.svg)](https://github.com/nanqinlang/Nginx)
[![license](https://github.com/nanqinlang/SVG/blob/master/license-GPLv3-orange.svg)](https://github.com/nanqinlang/Nginx)

## installation
```bash
./configure \
--prefix=/home/nginx \
--builddir=/home/nginx-installation/build \
--sbin-path=/home/nginx/sbin/nginx \
--modules-path=/home/nginx/modules \
--pid-path=/home/nginx/sbin/nginx.pid \
--conf-path=/home/nginx/conf/nginx.conf \
--error-log-path=/home/nginx/logs/error.log \
--lock-path=/home/nginx/lock/nginx.lock \
--http-client-body-temp-path=/home/nginx/temp/client_body \
--http-proxy-temp-path=/home/nginx/temp/proxy \
--with-pcre=/home/nginx-installation/pcre-8.37 \
--with-zlib=/home/nginx-installation/zlib-1.2.11 \
--with-openssl=/home/nginx-installation/openssl-draft-19 \
--with-openssl-opt=enable-tls1_3 \
--with-http_ssl_module \
--add-module=/home/nginx-installation/ct-module-1.3.2 \
--with-http_v2_module \
--with-http_realip_module \
--with-http_gzip_static_module \
--with-http_gunzip_module \
--with-http_sub_module \
--add-module=/home/nginx-installation/ngx_http_substitutions_filter_module \
--with-http_stub_status_module \
--with-file-aio \
--with-debug \
--with-http_degradation_module \
--with-http_flv_module \
--without-http_fastcgi_module \
--without-http_scgi_module \
--without-http_uwsgi_module \
--without-http_autoindex_module \
--without-http_charset_module \
--without-http_empty_gif_module \
--without-mail_pop3_module \
--without-mail_imap_module \
--without-mail_smtp_module
```

## according
https://sometimesnaive.org/
