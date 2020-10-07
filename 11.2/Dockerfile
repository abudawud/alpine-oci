FROM alpine

LABEL version="1.0"
LABEL maintainer="abudawud <warishafidz@gmail.com>"

RUN set -eux; \
	# add dependencie
	apk add libaio libnsl; \
	ln -s /usr/lib/libnsl.so.2 /usr/lib/libnsl.so.1; \
	wget https://raw.githubusercontent.com/abudawud/php-docker/master/fpm/5.6-oci/instantclient_11_2.tar.xz; \
	tar xJf instantclient_11_2.tar.xz; \
	mv instantclient_11_2 /usr/lib; \
	# setup client
	cd /usr/lib/instantclient_11_2; \
	ln /usr/lib/instantclient_11_2/libclntsh.so.11.1 /usr/lib/libclntsh.so; \
	ln /usr/lib/instantclient_11_2/libocci.so.11.1 /usr/lib/libocci.so; \
	ln /usr/lib/instantclient_11_2/libociei.so /usr/lib/libociei.so; \
	ln /usr/lib/instantclient_11_2/libnnz11.so /usr/lib/libnnz11.so; \
	ln -s libclntsh.so.11.1 libclntsh.so; \
	# cleaning
	cd - ; \
	rm instantclient_11_2.tar.xz
