# Nginx
[![Build Status](https://github.com/nanqinlang/SVG/blob/master/build%20passing.svg)](https://github.com/nanqinlang/Nginx)
[![language](https://github.com/nanqinlang/SVG/blob/master/language-shell-blue.svg)](https://github.com/nanqinlang/Nginx)
[![author](https://github.com/nanqinlang/SVG/blob/master/author-nanqinlang-lightgrey.svg)](https://github.com/nanqinlang/Nginx)
[![license](https://github.com/nanqinlang/SVG/blob/master/license-GPLv3-orange.svg)](https://github.com/nanqinlang/Nginx)

## installation
```bash
directory(){
	[[ ! -d /home/nginx-installation ]] && mkdir -p /home/nginx-installation
	cd /home/nginx-installation
}


get_pcre(){
	wget https://raw.githubusercontent.com/nanqinlang/Nginx/master/dependence/pcre-8.37.tar.gz && tar -zxf pcre-8.37.tar.gz
}


get_zlib(){
	wget https://raw.githubusercontent.com/nanqinlang/Nginx/master/dependence/zlib-1.2.11.tar.gz && tar -zxf zlib-1.2.11.tar.gz
}


get_openssl(){
	#draft 18
	git clone -b tls1.3-draft-18 https://github.com/nanqinlang-fork/openssl.git openssl-draft-18

	#draft 19
	git clone -b tls1.3-draft-19 https://github.com/nanqinlang-fork/openssl.git openssl-draft-19
}


get_nginx(){
	#nginx-1.13.6
	wget https://raw.githubusercontent.com/nanqinlang/Nginx/master/source/nginx-1.13.6.tar.gz && tar -zxf nginx-1.13.6.tar.gz

	#Nanqinlang/3.0.2
	wget https://raw.githubusercontent.com/nanqinlang/Nginx/master/source/nginx-nanqinlang.tar.gz && tar -zxf nginx-nanqinlang.tar.gz
}


get_substitutions_filter_module(){	
	git clone https://github.com/nanqinlang-fork/ngx_http_substitutions_filter_module.git
}


get_ct_module(){
	wget https://raw.githubusercontent.com/nanqinlang/Nginx/master/module/ct-module-1.3.2.tar.gz && tar -zxf ct-module-1.3.2.tar.gz
}


get_accesskey_module(){
	wget https://raw.githubusercontent.com/nanqinlang/Nginx/master/module/accesskey-module-2.0.3.tar.gz && tar -zxf accesskey-module-2.0.3.tar.gz
}



install(){
	chmod -R 7777 /home/nginx-installation
	cd /home/nginx-installation/nginx-nanqinlang

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

	make
	make install
}
```

## according
https://sometimesnaive.org/article/webfield/nginx/my-config-of-entirement