<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `composer`

-	[`composer:1`](#composer1)
-	[`composer:1.4`](#composer14)
-	[`composer:1.4.3`](#composer143)
-	[`composer:1.5`](#composer15)
-	[`composer:1.5.6`](#composer156)
-	[`composer:1.6`](#composer16)
-	[`composer:1.6.5`](#composer165)
-	[`composer:1.7`](#composer17)
-	[`composer:1.7.1`](#composer171)
-	[`composer:latest`](#composerlatest)

## `composer:1`

```console
$ docker pull composer@sha256:5c4bd89217b50125f28e08d9f16414ecb75f90ce9b773605472b35cd55f3e5c0
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1` - linux; amd64

```console
$ docker pull composer@sha256:4598feb4b58b4370893a29cbc654afa9420b4debed1d574531514b78a24cd608
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60877664 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:975a3ef6cb721f0f2e0250e55888c54901c8d46724e482b2a5b0457272a61885`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Wed, 08 Aug 2018 14:21:03 GMT
ENV COMPOSER_VERSION=1.7.1
# Wed, 08 Aug 2018 14:21:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Wed, 08 Aug 2018 14:21:06 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Wed, 08 Aug 2018 14:21:07 GMT
WORKDIR /app
# Wed, 08 Aug 2018 14:21:07 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Wed, 08 Aug 2018 14:21:07 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6259e38200519ed4c1b5cce053615ebda9b9c522a78b8295796beb6361983276`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c537a25439efc4805f8034f7c700c655428c969750d97b726a924d86a4167705`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7815569f023ac96506a58991996853c2de6e9693e3d21214474ad15477eec8c8`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:58110e28102837693c48b78e20a4ae006372d0d04e53a2f274ab0f567f8d010b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57566141 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:764b8f3e3e833049167962c8ddd6299ad70b0126445b0c4ab0d3cc9ebabc4fa5`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:40:01 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:40:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:40:07 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:40:08 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:40:09 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:40:10 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:708f0fe7ea48022eb967640c99bdf3fb1ee8aa2e76df63e3521b3a0e24c81451`  
		Last Modified: Thu, 09 Aug 2018 08:40:56 GMT  
		Size: 477.6 KB (477594 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d16550e500b75b0c87ff30ab95ca2469866fbfbafd580d1cf69f948119e6f5d`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0150f71df75175b17de0d25bf11c8e9f67bfaf65365bdd476878b015d1b424a3`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1` - linux; 386

```console
$ docker pull composer@sha256:77e535bb813bfddeca8aaa5e71ef953a347f385279110a112ab259d10e3f282e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.2 MB (62242744 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a1ee026fc0b33f194f258a43a130428090ac58af1cb1c10df8f34dcd40d00b7d`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 10:39:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 10:39:32 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 10:39:32 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 10:39:33 GMT
WORKDIR /app
# Thu, 09 Aug 2018 10:39:33 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 10:39:33 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed1f7abf488420dab6707be05f6c54b776e0349b116d7895e912f2a63ab576ba`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f58c659562e49e33a2db82cab277f7ebab85afbbf14b62409ae9c8f31c7c6f5`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b6284f9cf3688e2393a35c03c1ed5a887a1f003bd4b535da08db16afc7b4cff`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1` - linux; ppc64le

```console
$ docker pull composer@sha256:0cb72ddf9280661d3233126e371c008fdf3ee378f5ad509dfd45e8b83735c4eb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59484730 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6a70d48dde6a764474826327979dc33a85b872371fe643ec66721415be9eedb1`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:16:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:16:35 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:16:37 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:16:38 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:16:39 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:16:40 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98555166c596da13aa1972ec6d1714174d24bb23b22f372a7f6a739436ccde0b`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 477.6 KB (477590 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1fdf7b4b2db397e5057a7fe99b9bd37aa853dc6dafc02248da0e8c344a28ecb`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a9f064a9b5cc2ec9d54cfc0a012b3ec766bcac43d8f0842d985391ab04612e8`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.4`

```console
$ docker pull composer@sha256:b0ec0846f4f9dc133c23747c465c40e898a69669267540bac3e0e9aa313f49e9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.4` - linux; amd64

```console
$ docker pull composer@sha256:90459dd66461b444f09320746f6c8d630cf91cd00781cf683a032601e0550960
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60888233 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f2b2e8a3d247adc145e6a2473be4aa3aba51d9953cdfc19ec0b42463e5151dc9`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:29:08 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 13:29:10 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:29:11 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:29:11 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:29:11 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:29:12 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ceea6a7ade33f9b5c5eff2aa5445b637909688f62efb41840db553614d82464a`  
		Last Modified: Sat, 21 Jul 2018 13:31:47 GMT  
		Size: 488.2 KB (488163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:93c277e31f4777f7823952b518f4b4ce43338f05792690b9bfb02afbbe94688a`  
		Last Modified: Sat, 21 Jul 2018 13:31:46 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b48c511b25522bc86ab3be0b9d97b9708afe2f8d5c0474e5e0ba52da2bc77619`  
		Last Modified: Sat, 21 Jul 2018 13:31:46 GMT  
		Size: 90.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.4` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:d79fceb1f32a9552a19a898b001a523d7116f0b5752d9914b05e762263d6d9d3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57576708 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:38ebe83840eb9c11870a55d3a6d49dc703254c38a24924f0434e0161e2c98b31`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:45:03 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 17:45:06 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:45:07 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:45:08 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:45:08 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:45:09 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bca989a1cacaac0a4b5c06c1ce231f27e1fbc52e032074d4b830d46f31393d18`  
		Last Modified: Sat, 21 Jul 2018 17:47:44 GMT  
		Size: 488.2 KB (488160 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05815700ec9e2397262b3d598669ab24230d1aa7010c0bbfff126d7d3a633dd3`  
		Last Modified: Sat, 21 Jul 2018 17:47:43 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1c09e7e62a7ea3418404bc33afa630934419ce4342d257c8e76ee548539ac96`  
		Last Modified: Sat, 21 Jul 2018 17:47:43 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.4` - linux; 386

```console
$ docker pull composer@sha256:6687f5ae2be197f27363c89fbe777c4c229be3149c3fed4d3a511581c36bf203
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.3 MB (62253315 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:039727aff5a41da4593379892221337e0fd72e87a38b0afd38efae2512f83749`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:19:39 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 17:19:41 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:19:42 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:19:42 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:19:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:19:43 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d37e08fd0034e194b462df14f354a3fef619d70233c6fd890b6cab5ca2acc80`  
		Last Modified: Sat, 21 Jul 2018 17:22:22 GMT  
		Size: 488.2 KB (488163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1095f87216985eb19f70fae009e09c36635699c8072b0340bb6574e4ba974d05`  
		Last Modified: Sat, 21 Jul 2018 17:22:21 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4e993981ded840183959fe75138ca0546a8b51a212582f1134dc60844db4392`  
		Last Modified: Sat, 21 Jul 2018 17:22:21 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.4` - linux; ppc64le

```console
$ docker pull composer@sha256:5618bbbfdf3508cdaca5218911b0b249487dd0f37466a837df26a44067f16e8f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59495305 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:93409db9528b2dbbc5ae5ff1685d928f71fd8e450042d8107f60db0184dfd0ec`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:12:18 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 13:12:23 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:12:25 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:12:26 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:12:27 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:12:28 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4fbd37aac53e85a356a9a8aeaee6af870a8adc75fa3b8b5f4f86184f69c64f07`  
		Last Modified: Sat, 21 Jul 2018 13:14:11 GMT  
		Size: 488.2 KB (488164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65795cb912d198de12fbdb2f1da1dfb2b54cbeba9511c4cb5d1ae125fa8db1d4`  
		Last Modified: Sat, 21 Jul 2018 13:14:11 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e7527b4f9d6f36c236f679ab749beb560cb09d4588a187d2ecc688694e376fe`  
		Last Modified: Sat, 21 Jul 2018 13:14:11 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.4.3`

```console
$ docker pull composer@sha256:b0ec0846f4f9dc133c23747c465c40e898a69669267540bac3e0e9aa313f49e9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.4.3` - linux; amd64

```console
$ docker pull composer@sha256:90459dd66461b444f09320746f6c8d630cf91cd00781cf683a032601e0550960
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60888233 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f2b2e8a3d247adc145e6a2473be4aa3aba51d9953cdfc19ec0b42463e5151dc9`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:29:08 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 13:29:10 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:29:11 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:29:11 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:29:11 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:29:12 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ceea6a7ade33f9b5c5eff2aa5445b637909688f62efb41840db553614d82464a`  
		Last Modified: Sat, 21 Jul 2018 13:31:47 GMT  
		Size: 488.2 KB (488163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:93c277e31f4777f7823952b518f4b4ce43338f05792690b9bfb02afbbe94688a`  
		Last Modified: Sat, 21 Jul 2018 13:31:46 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b48c511b25522bc86ab3be0b9d97b9708afe2f8d5c0474e5e0ba52da2bc77619`  
		Last Modified: Sat, 21 Jul 2018 13:31:46 GMT  
		Size: 90.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.4.3` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:d79fceb1f32a9552a19a898b001a523d7116f0b5752d9914b05e762263d6d9d3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57576708 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:38ebe83840eb9c11870a55d3a6d49dc703254c38a24924f0434e0161e2c98b31`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:45:03 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 17:45:06 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:45:07 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:45:08 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:45:08 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:45:09 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bca989a1cacaac0a4b5c06c1ce231f27e1fbc52e032074d4b830d46f31393d18`  
		Last Modified: Sat, 21 Jul 2018 17:47:44 GMT  
		Size: 488.2 KB (488160 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05815700ec9e2397262b3d598669ab24230d1aa7010c0bbfff126d7d3a633dd3`  
		Last Modified: Sat, 21 Jul 2018 17:47:43 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1c09e7e62a7ea3418404bc33afa630934419ce4342d257c8e76ee548539ac96`  
		Last Modified: Sat, 21 Jul 2018 17:47:43 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.4.3` - linux; 386

```console
$ docker pull composer@sha256:6687f5ae2be197f27363c89fbe777c4c229be3149c3fed4d3a511581c36bf203
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.3 MB (62253315 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:039727aff5a41da4593379892221337e0fd72e87a38b0afd38efae2512f83749`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:19:39 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 17:19:41 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:19:42 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:19:42 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:19:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:19:43 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d37e08fd0034e194b462df14f354a3fef619d70233c6fd890b6cab5ca2acc80`  
		Last Modified: Sat, 21 Jul 2018 17:22:22 GMT  
		Size: 488.2 KB (488163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1095f87216985eb19f70fae009e09c36635699c8072b0340bb6574e4ba974d05`  
		Last Modified: Sat, 21 Jul 2018 17:22:21 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4e993981ded840183959fe75138ca0546a8b51a212582f1134dc60844db4392`  
		Last Modified: Sat, 21 Jul 2018 17:22:21 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.4.3` - linux; ppc64le

```console
$ docker pull composer@sha256:5618bbbfdf3508cdaca5218911b0b249487dd0f37466a837df26a44067f16e8f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59495305 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:93409db9528b2dbbc5ae5ff1685d928f71fd8e450042d8107f60db0184dfd0ec`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:12:18 GMT
ENV COMPOSER_VERSION=1.4.3
# Sat, 21 Jul 2018 13:12:23 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:12:25 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:12:26 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:12:27 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:12:28 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4fbd37aac53e85a356a9a8aeaee6af870a8adc75fa3b8b5f4f86184f69c64f07`  
		Last Modified: Sat, 21 Jul 2018 13:14:11 GMT  
		Size: 488.2 KB (488164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65795cb912d198de12fbdb2f1da1dfb2b54cbeba9511c4cb5d1ae125fa8db1d4`  
		Last Modified: Sat, 21 Jul 2018 13:14:11 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e7527b4f9d6f36c236f679ab749beb560cb09d4588a187d2ecc688694e376fe`  
		Last Modified: Sat, 21 Jul 2018 13:14:11 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.5`

```console
$ docker pull composer@sha256:b277d79e43288f4c0a74cd2928e5751edef77c1c48513fedafae7ff13a376c05
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.5` - linux; amd64

```console
$ docker pull composer@sha256:4443bf1131e93be8eea1868e0b12652a07203321fb9cc239d537910bb018cce3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60889653 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8a250c3ea91c2f267e3d48d579dda0168e510edbf0ce340e7986bd424fbb9ce3`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:28:47 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 13:28:49 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:28:50 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:28:50 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:28:50 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:28:50 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39dfaf00cf80f43e4fb8071e8e995ef104dba706fb5b4ed9e7bf670564e44df8`  
		Last Modified: Sat, 21 Jul 2018 13:31:00 GMT  
		Size: 489.6 KB (489581 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f1701615d1e69d5809c8045962cdd91895be57a8ca0dbf24d75806e1d60933b`  
		Last Modified: Sat, 21 Jul 2018 13:30:59 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6156050a8295e3d22263381ac2df0ae7ed9845bcd15a5a50dd1db1bdf4a55b22`  
		Last Modified: Sat, 21 Jul 2018 13:31:00 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.5` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:cf8ae6505dead19de2dda24b36fba35f7a5c046c893e0b4ae535e18daa806878
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57578127 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7b964769ba25fc2468ee11f7aa2027291e2f1fa4fa87d4d6446ae0d080a92d3f`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:44:38 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 17:44:42 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:44:42 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:44:43 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:44:44 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:44:45 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c84d1fecf4f795f6e46e68dbe437defe8bf928a5a93be40ffb5e96afe1e329d5`  
		Last Modified: Sat, 21 Jul 2018 17:46:57 GMT  
		Size: 489.6 KB (489579 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85ae866c9a85ac2d5f2920d1256082ee4cf0f7ba41175089d6283c1c9540ea9d`  
		Last Modified: Sat, 21 Jul 2018 17:46:57 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f2b3d43d972285b786c85c395caddac85ce29ef6f3a1681a1c156bf8726c8e1`  
		Last Modified: Sat, 21 Jul 2018 17:46:57 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.5` - linux; 386

```console
$ docker pull composer@sha256:5e2d003b600c52210803f922afc39a3eb6c7a4bbb71b4d4c856527f5ba595c0d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.3 MB (62254730 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8036e34f0db1c582afa41066c98c0d1d406ab103c46d04116f84102b04fb8622`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:19:22 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 17:19:25 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:19:25 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:19:25 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:19:26 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:19:26 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16e6cd9793c886e3d40ba825615a05879407e84d2ac07082413351aed0cae194`  
		Last Modified: Sat, 21 Jul 2018 17:21:44 GMT  
		Size: 489.6 KB (489578 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c8fc5cfa6fee4f4c6a8bc9b88fdf2c5623aa5d8f9141255dc43b92a95ba24b1`  
		Last Modified: Sat, 21 Jul 2018 17:21:44 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d4f8badbba7ff83991eab923dc92881f0103405d1f41d6839825236392d1578`  
		Last Modified: Sat, 21 Jul 2018 17:21:44 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.5` - linux; ppc64le

```console
$ docker pull composer@sha256:4b4ffecbf0777b4408addc6c1541cd5613c8c19760af0cfdafcbf5d14f70d6df
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59496721 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a446b434688626a756dfbbaeb71c00efa78a137f12bab67b47827deba77f13c8`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:11:53 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 13:11:59 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:12:01 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:12:03 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:12:06 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:12:08 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2e5daf425a7e81444a8f90e9c35cd2e47ffb19a728905213ea6fdada432900c`  
		Last Modified: Sat, 21 Jul 2018 13:13:46 GMT  
		Size: 489.6 KB (489578 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:525ef9d03588966405c502c7e0347f880e623fb6014f12dc0d73cb599c6794cf`  
		Last Modified: Sat, 21 Jul 2018 13:13:46 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cb07036488f4c34d59d9037f918fb4776a8008273f4d116aee796fe51d61864`  
		Last Modified: Sat, 21 Jul 2018 13:13:46 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.5.6`

```console
$ docker pull composer@sha256:b277d79e43288f4c0a74cd2928e5751edef77c1c48513fedafae7ff13a376c05
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.5.6` - linux; amd64

```console
$ docker pull composer@sha256:4443bf1131e93be8eea1868e0b12652a07203321fb9cc239d537910bb018cce3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60889653 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8a250c3ea91c2f267e3d48d579dda0168e510edbf0ce340e7986bd424fbb9ce3`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:28:47 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 13:28:49 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:28:50 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:28:50 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:28:50 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:28:50 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39dfaf00cf80f43e4fb8071e8e995ef104dba706fb5b4ed9e7bf670564e44df8`  
		Last Modified: Sat, 21 Jul 2018 13:31:00 GMT  
		Size: 489.6 KB (489581 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f1701615d1e69d5809c8045962cdd91895be57a8ca0dbf24d75806e1d60933b`  
		Last Modified: Sat, 21 Jul 2018 13:30:59 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6156050a8295e3d22263381ac2df0ae7ed9845bcd15a5a50dd1db1bdf4a55b22`  
		Last Modified: Sat, 21 Jul 2018 13:31:00 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.5.6` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:cf8ae6505dead19de2dda24b36fba35f7a5c046c893e0b4ae535e18daa806878
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57578127 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7b964769ba25fc2468ee11f7aa2027291e2f1fa4fa87d4d6446ae0d080a92d3f`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:44:38 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 17:44:42 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:44:42 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:44:43 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:44:44 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:44:45 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c84d1fecf4f795f6e46e68dbe437defe8bf928a5a93be40ffb5e96afe1e329d5`  
		Last Modified: Sat, 21 Jul 2018 17:46:57 GMT  
		Size: 489.6 KB (489579 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85ae866c9a85ac2d5f2920d1256082ee4cf0f7ba41175089d6283c1c9540ea9d`  
		Last Modified: Sat, 21 Jul 2018 17:46:57 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f2b3d43d972285b786c85c395caddac85ce29ef6f3a1681a1c156bf8726c8e1`  
		Last Modified: Sat, 21 Jul 2018 17:46:57 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.5.6` - linux; 386

```console
$ docker pull composer@sha256:5e2d003b600c52210803f922afc39a3eb6c7a4bbb71b4d4c856527f5ba595c0d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.3 MB (62254730 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8036e34f0db1c582afa41066c98c0d1d406ab103c46d04116f84102b04fb8622`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:19:22 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 17:19:25 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:19:25 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:19:25 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:19:26 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:19:26 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16e6cd9793c886e3d40ba825615a05879407e84d2ac07082413351aed0cae194`  
		Last Modified: Sat, 21 Jul 2018 17:21:44 GMT  
		Size: 489.6 KB (489578 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c8fc5cfa6fee4f4c6a8bc9b88fdf2c5623aa5d8f9141255dc43b92a95ba24b1`  
		Last Modified: Sat, 21 Jul 2018 17:21:44 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d4f8badbba7ff83991eab923dc92881f0103405d1f41d6839825236392d1578`  
		Last Modified: Sat, 21 Jul 2018 17:21:44 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.5.6` - linux; ppc64le

```console
$ docker pull composer@sha256:4b4ffecbf0777b4408addc6c1541cd5613c8c19760af0cfdafcbf5d14f70d6df
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59496721 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a446b434688626a756dfbbaeb71c00efa78a137f12bab67b47827deba77f13c8`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:11:53 GMT
ENV COMPOSER_VERSION=1.5.6
# Sat, 21 Jul 2018 13:11:59 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:12:01 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:12:03 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:12:06 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:12:08 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2e5daf425a7e81444a8f90e9c35cd2e47ffb19a728905213ea6fdada432900c`  
		Last Modified: Sat, 21 Jul 2018 13:13:46 GMT  
		Size: 489.6 KB (489578 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:525ef9d03588966405c502c7e0347f880e623fb6014f12dc0d73cb599c6794cf`  
		Last Modified: Sat, 21 Jul 2018 13:13:46 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cb07036488f4c34d59d9037f918fb4776a8008273f4d116aee796fe51d61864`  
		Last Modified: Sat, 21 Jul 2018 13:13:46 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.6`

```console
$ docker pull composer@sha256:f3c526a0cca51870ea0edb7895df25910cbf2d56be8d901a68659e1175377080
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.6` - linux; amd64

```console
$ docker pull composer@sha256:dfecc6ef75af65ae54e98a931072e605786ada524a11c345c766d64658ff19ee
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60872284 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:939cf684b4cb67b196114e75be1d627f62e0013229d672cae4b83c8fb6d8c9da`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:28:18 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 13:28:20 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:28:21 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:28:21 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:28:21 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:28:22 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89ce67e84d0a38b653ae914955486e790cc63b13ad256977ff74746329e8af9f`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 472.2 KB (472211 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ac00e25cbfbb11194b400d1917d56afb1e7073a0f23a20f36dcf373be1af651`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:963478629c6894175fed438484b222281d4643e0ec106ee6562d6862ef2170ce`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.6` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:1dc1ac08560fb17dd778401bd5325d3d5bc92aac33e683857a9cc143031b56d4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57560757 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5631e82228c3ca019c836424bbbccda73683c88fca766e90f32829370b3c4a2c`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:43:49 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 17:43:55 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:43:56 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:43:56 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:43:57 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:43:58 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03ec9b838f3e03519fe2d029283ba0b3024a170253b1a0459902fe9c1c5a3462`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 472.2 KB (472208 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f8b16fcff1771efc9d938fceeb4eaf0e297154f9ac7355b5c49d77efb56aa8d`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d3840494f994a0729f99e75b82974cf4c0e577b48e606fbd06f2276caa20752`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.6` - linux; 386

```console
$ docker pull composer@sha256:35b2b1f44accc8b2a864ad38d90d4f4c185eaf6f33fcb1c8ff698ceca4ce7758
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.2 MB (62237362 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fda9c8da3be7a342aa153eb84762eb68d74614ddc12ac31629c7be031a1580b4`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 17:18:58 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:18:58 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:18:59 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:18:59 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:18:59 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbe4b276b22d844a5226587b2b0461a15b67f93689aa953749c95418358c1e1c`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 472.2 KB (472212 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4c2c9e8db4b50201e480bfcc7fc5341c3ddcac467c0642ca24f4ed14599acc8`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fee18d773abb4ead73519f9cbcf521a311bf98e04a3d024ca9615853593044f`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.6` - linux; ppc64le

```console
$ docker pull composer@sha256:ea7d0362e2a37cf1c01b0224269eeb6f9be6a45dddc3f90266b4b1188e217a8a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59479352 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:323363cf4253d46ccffe59b89ace21475f689bf0650e68bfa8e3d8cd34a4de70`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 13:11:09 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:11:14 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:11:29 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:11:31 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:11:32 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1420f0d9f50bfffaa9db3a272a2c6c9f5d75d5392de7e21742087a4f40a9052`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 472.2 KB (472211 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64e5ad2455f0316160eed68aa8bfd2471449a17212b8afa131905d98e052d5d7`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f5a9dba601df843faedb888619e44b82b722fab6f5c4938adb2a67e82dfa28a`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.6.5`

```console
$ docker pull composer@sha256:f3c526a0cca51870ea0edb7895df25910cbf2d56be8d901a68659e1175377080
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.6.5` - linux; amd64

```console
$ docker pull composer@sha256:dfecc6ef75af65ae54e98a931072e605786ada524a11c345c766d64658ff19ee
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60872284 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:939cf684b4cb67b196114e75be1d627f62e0013229d672cae4b83c8fb6d8c9da`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:28:18 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 13:28:20 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:28:21 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:28:21 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:28:21 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:28:22 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89ce67e84d0a38b653ae914955486e790cc63b13ad256977ff74746329e8af9f`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 472.2 KB (472211 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ac00e25cbfbb11194b400d1917d56afb1e7073a0f23a20f36dcf373be1af651`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 537.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:963478629c6894175fed438484b222281d4643e0ec106ee6562d6862ef2170ce`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.6.5` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:1dc1ac08560fb17dd778401bd5325d3d5bc92aac33e683857a9cc143031b56d4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57560757 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5631e82228c3ca019c836424bbbccda73683c88fca766e90f32829370b3c4a2c`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:43:49 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 17:43:55 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:43:56 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:43:56 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:43:57 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:43:58 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03ec9b838f3e03519fe2d029283ba0b3024a170253b1a0459902fe9c1c5a3462`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 472.2 KB (472208 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f8b16fcff1771efc9d938fceeb4eaf0e297154f9ac7355b5c49d77efb56aa8d`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d3840494f994a0729f99e75b82974cf4c0e577b48e606fbd06f2276caa20752`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.6.5` - linux; 386

```console
$ docker pull composer@sha256:35b2b1f44accc8b2a864ad38d90d4f4c185eaf6f33fcb1c8ff698ceca4ce7758
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.2 MB (62237362 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fda9c8da3be7a342aa153eb84762eb68d74614ddc12ac31629c7be031a1580b4`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 17:18:58 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 17:18:58 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 17:18:59 GMT
WORKDIR /app
# Sat, 21 Jul 2018 17:18:59 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 17:18:59 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbe4b276b22d844a5226587b2b0461a15b67f93689aa953749c95418358c1e1c`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 472.2 KB (472212 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4c2c9e8db4b50201e480bfcc7fc5341c3ddcac467c0642ca24f4ed14599acc8`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fee18d773abb4ead73519f9cbcf521a311bf98e04a3d024ca9615853593044f`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.6.5` - linux; ppc64le

```console
$ docker pull composer@sha256:ea7d0362e2a37cf1c01b0224269eeb6f9be6a45dddc3f90266b4b1188e217a8a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59479352 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:323363cf4253d46ccffe59b89ace21475f689bf0650e68bfa8e3d8cd34a4de70`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_VERSION=1.6.5
# Sat, 21 Jul 2018 13:11:09 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Sat, 21 Jul 2018 13:11:14 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Sat, 21 Jul 2018 13:11:29 GMT
WORKDIR /app
# Sat, 21 Jul 2018 13:11:31 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 21 Jul 2018 13:11:32 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1420f0d9f50bfffaa9db3a272a2c6c9f5d75d5392de7e21742087a4f40a9052`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 472.2 KB (472211 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64e5ad2455f0316160eed68aa8bfd2471449a17212b8afa131905d98e052d5d7`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f5a9dba601df843faedb888619e44b82b722fab6f5c4938adb2a67e82dfa28a`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.7`

```console
$ docker pull composer@sha256:5c4bd89217b50125f28e08d9f16414ecb75f90ce9b773605472b35cd55f3e5c0
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.7` - linux; amd64

```console
$ docker pull composer@sha256:4598feb4b58b4370893a29cbc654afa9420b4debed1d574531514b78a24cd608
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60877664 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:975a3ef6cb721f0f2e0250e55888c54901c8d46724e482b2a5b0457272a61885`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Wed, 08 Aug 2018 14:21:03 GMT
ENV COMPOSER_VERSION=1.7.1
# Wed, 08 Aug 2018 14:21:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Wed, 08 Aug 2018 14:21:06 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Wed, 08 Aug 2018 14:21:07 GMT
WORKDIR /app
# Wed, 08 Aug 2018 14:21:07 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Wed, 08 Aug 2018 14:21:07 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6259e38200519ed4c1b5cce053615ebda9b9c522a78b8295796beb6361983276`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c537a25439efc4805f8034f7c700c655428c969750d97b726a924d86a4167705`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7815569f023ac96506a58991996853c2de6e9693e3d21214474ad15477eec8c8`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.7` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:58110e28102837693c48b78e20a4ae006372d0d04e53a2f274ab0f567f8d010b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57566141 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:764b8f3e3e833049167962c8ddd6299ad70b0126445b0c4ab0d3cc9ebabc4fa5`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:40:01 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:40:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:40:07 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:40:08 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:40:09 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:40:10 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:708f0fe7ea48022eb967640c99bdf3fb1ee8aa2e76df63e3521b3a0e24c81451`  
		Last Modified: Thu, 09 Aug 2018 08:40:56 GMT  
		Size: 477.6 KB (477594 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d16550e500b75b0c87ff30ab95ca2469866fbfbafd580d1cf69f948119e6f5d`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0150f71df75175b17de0d25bf11c8e9f67bfaf65365bdd476878b015d1b424a3`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.7` - linux; 386

```console
$ docker pull composer@sha256:77e535bb813bfddeca8aaa5e71ef953a347f385279110a112ab259d10e3f282e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.2 MB (62242744 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a1ee026fc0b33f194f258a43a130428090ac58af1cb1c10df8f34dcd40d00b7d`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 10:39:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 10:39:32 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 10:39:32 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 10:39:33 GMT
WORKDIR /app
# Thu, 09 Aug 2018 10:39:33 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 10:39:33 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed1f7abf488420dab6707be05f6c54b776e0349b116d7895e912f2a63ab576ba`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f58c659562e49e33a2db82cab277f7ebab85afbbf14b62409ae9c8f31c7c6f5`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b6284f9cf3688e2393a35c03c1ed5a887a1f003bd4b535da08db16afc7b4cff`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.7` - linux; ppc64le

```console
$ docker pull composer@sha256:0cb72ddf9280661d3233126e371c008fdf3ee378f5ad509dfd45e8b83735c4eb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59484730 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6a70d48dde6a764474826327979dc33a85b872371fe643ec66721415be9eedb1`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:16:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:16:35 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:16:37 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:16:38 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:16:39 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:16:40 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98555166c596da13aa1972ec6d1714174d24bb23b22f372a7f6a739436ccde0b`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 477.6 KB (477590 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1fdf7b4b2db397e5057a7fe99b9bd37aa853dc6dafc02248da0e8c344a28ecb`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a9f064a9b5cc2ec9d54cfc0a012b3ec766bcac43d8f0842d985391ab04612e8`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.7.1`

```console
$ docker pull composer@sha256:5c4bd89217b50125f28e08d9f16414ecb75f90ce9b773605472b35cd55f3e5c0
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:1.7.1` - linux; amd64

```console
$ docker pull composer@sha256:4598feb4b58b4370893a29cbc654afa9420b4debed1d574531514b78a24cd608
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60877664 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:975a3ef6cb721f0f2e0250e55888c54901c8d46724e482b2a5b0457272a61885`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Wed, 08 Aug 2018 14:21:03 GMT
ENV COMPOSER_VERSION=1.7.1
# Wed, 08 Aug 2018 14:21:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Wed, 08 Aug 2018 14:21:06 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Wed, 08 Aug 2018 14:21:07 GMT
WORKDIR /app
# Wed, 08 Aug 2018 14:21:07 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Wed, 08 Aug 2018 14:21:07 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6259e38200519ed4c1b5cce053615ebda9b9c522a78b8295796beb6361983276`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c537a25439efc4805f8034f7c700c655428c969750d97b726a924d86a4167705`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7815569f023ac96506a58991996853c2de6e9693e3d21214474ad15477eec8c8`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.7.1` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:58110e28102837693c48b78e20a4ae006372d0d04e53a2f274ab0f567f8d010b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57566141 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:764b8f3e3e833049167962c8ddd6299ad70b0126445b0c4ab0d3cc9ebabc4fa5`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:40:01 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:40:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:40:07 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:40:08 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:40:09 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:40:10 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:708f0fe7ea48022eb967640c99bdf3fb1ee8aa2e76df63e3521b3a0e24c81451`  
		Last Modified: Thu, 09 Aug 2018 08:40:56 GMT  
		Size: 477.6 KB (477594 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d16550e500b75b0c87ff30ab95ca2469866fbfbafd580d1cf69f948119e6f5d`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0150f71df75175b17de0d25bf11c8e9f67bfaf65365bdd476878b015d1b424a3`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.7.1` - linux; 386

```console
$ docker pull composer@sha256:77e535bb813bfddeca8aaa5e71ef953a347f385279110a112ab259d10e3f282e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.2 MB (62242744 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a1ee026fc0b33f194f258a43a130428090ac58af1cb1c10df8f34dcd40d00b7d`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 10:39:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 10:39:32 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 10:39:32 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 10:39:33 GMT
WORKDIR /app
# Thu, 09 Aug 2018 10:39:33 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 10:39:33 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed1f7abf488420dab6707be05f6c54b776e0349b116d7895e912f2a63ab576ba`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f58c659562e49e33a2db82cab277f7ebab85afbbf14b62409ae9c8f31c7c6f5`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b6284f9cf3688e2393a35c03c1ed5a887a1f003bd4b535da08db16afc7b4cff`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:1.7.1` - linux; ppc64le

```console
$ docker pull composer@sha256:0cb72ddf9280661d3233126e371c008fdf3ee378f5ad509dfd45e8b83735c4eb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59484730 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6a70d48dde6a764474826327979dc33a85b872371fe643ec66721415be9eedb1`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:16:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:16:35 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:16:37 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:16:38 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:16:39 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:16:40 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98555166c596da13aa1972ec6d1714174d24bb23b22f372a7f6a739436ccde0b`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 477.6 KB (477590 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1fdf7b4b2db397e5057a7fe99b9bd37aa853dc6dafc02248da0e8c344a28ecb`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a9f064a9b5cc2ec9d54cfc0a012b3ec766bcac43d8f0842d985391ab04612e8`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:latest`

```console
$ docker pull composer@sha256:5c4bd89217b50125f28e08d9f16414ecb75f90ce9b773605472b35cd55f3e5c0
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `composer:latest` - linux; amd64

```console
$ docker pull composer@sha256:4598feb4b58b4370893a29cbc654afa9420b4debed1d574531514b78a24cd608
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **60.9 MB (60877664 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:975a3ef6cb721f0f2e0250e55888c54901c8d46724e482b2a5b0457272a61885`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:45 GMT
ADD file:6ee19b92d5cb1bf143947fe2e2481cb3b353d42e1e54888a8ba48c03dd4155f2 in / 
# Fri, 06 Jul 2018 14:13:45 GMT
CMD ["/bin/sh"]
# Fri, 06 Jul 2018 16:18:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 06 Jul 2018 16:18:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 06 Jul 2018 16:18:41 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 06 Jul 2018 16:18:41 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 06 Jul 2018 16:18:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:42 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 06 Jul 2018 16:18:43 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 06 Jul 2018 16:18:43 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 08:03:18 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 08:03:19 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 08:03:27 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 08:03:41 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:06:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 08:07:00 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 08:07:02 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 08:07:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 08:07:03 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:27:38 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:27:39 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:28:17 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:28:17 GMT
ENV COMPOSER_HOME=/tmp
# Wed, 08 Aug 2018 14:21:03 GMT
ENV COMPOSER_VERSION=1.7.1
# Wed, 08 Aug 2018 14:21:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Wed, 08 Aug 2018 14:21:06 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Wed, 08 Aug 2018 14:21:07 GMT
WORKDIR /app
# Wed, 08 Aug 2018 14:21:07 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Wed, 08 Aug 2018 14:21:07 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:911c6d0c7995e5d9763c1864d54fb6deccda04a55d7955123a8e22dd9d44c497`  
		Last Modified: Fri, 06 Jul 2018 14:16:43 GMT  
		Size: 2.1 MB (2103553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2527cc05836df8b883384a19f35597b62f1e1ef30211c870fb5527e3080a6f58`  
		Last Modified: Fri, 06 Jul 2018 18:03:03 GMT  
		Size: 1.3 MB (1256023 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3299172a2d6d097e545dc05d7704c6a14168c66aa3e250a41ab825f94ab90b63`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05782106624fe89fa24d92965e55266bc688607d27223c74ced4be2fcaedb024`  
		Last Modified: Fri, 06 Jul 2018 18:03:01 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b50426d207f82ae92c77b3d55fb6ccee8ac4021852f2bd2360fe5d259006650`  
		Last Modified: Sat, 21 Jul 2018 11:09:43 GMT  
		Size: 13.4 MB (13394372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70ab55f391d4946e2ba7d932045f3a0a015d6a45c09ae0ea8dfae21ca804d7b7`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21c484c5f8ad0782a582153275b216a0cd74ad1eedba16aa76583f87d1bbb835`  
		Last Modified: Sat, 21 Jul 2018 11:09:45 GMT  
		Size: 15.9 MB (15922349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:306964342122be7f5c3850e9f24de321addb967d2d665b144b22d4f4b13ff989`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad00b4d20e137f34b23e1f62c43ebc34c0760d792e2beed3541a508f95bca2e0`  
		Last Modified: Sat, 21 Jul 2018 11:09:40 GMT  
		Size: 70.9 KB (70910 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926fe84fc40eb4ea7302a0db16c9b028c103b3169df84802b7515705d2e98e5`  
		Last Modified: Sat, 21 Jul 2018 13:29:45 GMT  
		Size: 26.2 MB (26196665 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49537206606666baaebf451160966d9d8ba7b21c4abc39d09e4953d32922fdbf`  
		Last Modified: Sat, 21 Jul 2018 13:29:32 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ef32abfda34c5049bfd0660fc75c206ea929ec5914d66fe15994c0e7609247`  
		Last Modified: Sat, 21 Jul 2018 13:29:33 GMT  
		Size: 1.5 MB (1451201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6259e38200519ed4c1b5cce053615ebda9b9c522a78b8295796beb6361983276`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c537a25439efc4805f8034f7c700c655428c969750d97b726a924d86a4167705`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 535.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7815569f023ac96506a58991996853c2de6e9693e3d21214474ad15477eec8c8`  
		Last Modified: Wed, 08 Aug 2018 14:21:51 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:latest` - linux; arm64 variant v8

```console
$ docker pull composer@sha256:58110e28102837693c48b78e20a4ae006372d0d04e53a2f274ab0f567f8d010b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.6 MB (57566141 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:764b8f3e3e833049167962c8ddd6299ad70b0126445b0c4ab0d3cc9ebabc4fa5`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 03:34:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 03:34:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 03:34:31 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 03:34:32 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 03:34:34 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 03:34:34 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 03:34:35 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 03:34:36 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:20:25 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:20:26 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:20:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:20:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:54 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:28:56 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:28:58 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:28:59 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:29:00 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:42:52 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:42:54 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:43:46 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:43:47 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:43:48 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:40:01 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:40:06 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:40:07 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:40:08 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:40:09 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:40:10 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3fd85926acf4e07a36e9605843329449387bbfc1c1550485a341b4f87bfe40c`  
		Last Modified: Sat, 16 Dec 2017 16:37:16 GMT  
		Size: 1.2 MB (1214054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cbd52b402d6ede87c727a4c39eca929bb27c7d5873fadd61ad1fc86752cc164`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a1ea5fa010452e4ef78628eebe6459b693eee1ec67ce04afd2ef50a2edee5fb`  
		Last Modified: Sat, 16 Dec 2017 16:37:15 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:925fce85261c0790efda90f1d01ab027bf4f3f7ffc86c278dffc1ff64609c655`  
		Last Modified: Sat, 21 Jul 2018 15:43:58 GMT  
		Size: 12.2 MB (12172871 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a300d40ab6e0dcde5d0b8afaf2bfdd746cf0219a273dac7f7165c83ef159141b`  
		Last Modified: Sat, 21 Jul 2018 15:43:57 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3632b0dec55e8cc3bf7fd0b84cd3ec935edd4bc1bb39eab791af027b6692bda5`  
		Last Modified: Sat, 21 Jul 2018 15:44:05 GMT  
		Size: 16.2 MB (16182604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6a4735dc52970754d262c7b1a3f2ded96d9ddf60120489731ae7433b872734`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 2.2 KB (2170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adde73e4e5cda7424076c3313d131878826c840c03fb8422230f8e7633b575ba`  
		Last Modified: Sat, 21 Jul 2018 15:43:56 GMT  
		Size: 69.9 KB (69869 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:071cc6ad81a4f0c55eb230799483f316e60a8ca043b9d48d5d77772dddb26c2d`  
		Last Modified: Sat, 21 Jul 2018 17:45:46 GMT  
		Size: 25.2 MB (25236571 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0fc5612b2290777564622a152461201ede566fedd298ba16b7961f268a3a583`  
		Last Modified: Sat, 21 Jul 2018 17:45:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c3a22478ac179fb8d5bcb8041fefadbf2fbb9ca57dfc56006deb5f488ee688`  
		Last Modified: Sat, 21 Jul 2018 17:45:33 GMT  
		Size: 218.5 KB (218548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:708f0fe7ea48022eb967640c99bdf3fb1ee8aa2e76df63e3521b3a0e24c81451`  
		Last Modified: Thu, 09 Aug 2018 08:40:56 GMT  
		Size: 477.6 KB (477594 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d16550e500b75b0c87ff30ab95ca2469866fbfbafd580d1cf69f948119e6f5d`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0150f71df75175b17de0d25bf11c8e9f67bfaf65365bdd476878b015d1b424a3`  
		Last Modified: Thu, 09 Aug 2018 08:40:55 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:latest` - linux; 386

```console
$ docker pull composer@sha256:77e535bb813bfddeca8aaa5e71ef953a347f385279110a112ab259d10e3f282e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.2 MB (62242744 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a1ee026fc0b33f194f258a43a130428090ac58af1cb1c10df8f34dcd40d00b7d`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:46:28 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Jun 2018 10:46:29 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Jun 2018 10:46:30 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Jun 2018 10:46:30 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Jun 2018 10:46:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Jun 2018 10:46:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Jun 2018 10:46:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 11:50:33 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 11:50:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 11:50:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:43 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 11:54:44 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 11:54:46 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 11:54:46 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 11:54:46 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 17:18:09 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 17:18:10 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 17:18:55 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 17:18:55 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 10:39:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 10:39:32 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 10:39:32 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 10:39:33 GMT
WORKDIR /app
# Thu, 09 Aug 2018 10:39:33 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 10:39:33 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9362910160aaa343ca8dc990efe62fff5a14089c10259744982d255c0638cb55`  
		Last Modified: Fri, 01 Jun 2018 11:43:26 GMT  
		Size: 1.4 MB (1368704 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:978adc59089609682b6befe63f957c0e68bd015afa73c26179064798a98bccfd`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 1.3 KB (1252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13520db38890805ee92c3c897f635d68fe93da65b7a2fd8b9d15270589cba60c`  
		Last Modified: Fri, 01 Jun 2018 11:43:25 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87f8df4c7b620b7d2ff06595752a94f6f92bcc36b54bee77552627d515abf371`  
		Last Modified: Sat, 21 Jul 2018 15:24:09 GMT  
		Size: 12.2 MB (12172920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81498286a1bfa12a0bcfb199d845126d8abb09b3f48f33ef26f9ab905609cdc3`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d166b0ecbd328150d988c6efecccebc73d48397124800655177db099ddd2604`  
		Last Modified: Sat, 21 Jul 2018 15:24:17 GMT  
		Size: 18.0 MB (17977092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b22215da1b353b0fcd577a75689d54443bf885af0d7cf0007f6dfd317dec27`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 2.2 KB (2167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecc18d2cd7096fb9a8d71f3cd4f0c5010181b0f05ccdfe1fecdcc68b6284cc4a`  
		Last Modified: Sat, 21 Jul 2018 15:24:07 GMT  
		Size: 70.1 KB (70147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:303befad8783b9a3776b312c04f2a2d247d1d1bc7f1de35e8bee3471d8fb0165`  
		Last Modified: Sat, 21 Jul 2018 17:20:18 GMT  
		Size: 27.8 MB (27802327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f9541186e8a066fde5010eb9024ca7d40b77599750f8262ce8747d5dc1efa52`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eeaa703a7356130764f20f22b0ce0bded0ba6ebd645edbd2cde96b17bcdfe68e`  
		Last Modified: Sat, 21 Jul 2018 17:20:02 GMT  
		Size: 242.6 KB (242572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed1f7abf488420dab6707be05f6c54b776e0349b116d7895e912f2a63ab576ba`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 477.6 KB (477593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f58c659562e49e33a2db82cab277f7ebab85afbbf14b62409ae9c8f31c7c6f5`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 536.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b6284f9cf3688e2393a35c03c1ed5a887a1f003bd4b535da08db16afc7b4cff`  
		Last Modified: Thu, 09 Aug 2018 10:40:01 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `composer:latest` - linux; ppc64le

```console
$ docker pull composer@sha256:0cb72ddf9280661d3233126e371c008fdf3ee378f5ad509dfd45e8b83735c4eb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **59.5 MB (59484730 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6a70d48dde6a764474826327979dc33a85b872371fe643ec66721415be9eedb1`
-	Entrypoint: `["\/bin\/sh","\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Thu, 14 Dec 2017 09:49:48 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Thu, 14 Dec 2017 09:50:02 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Thu, 14 Dec 2017 09:50:06 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Thu, 14 Dec 2017 09:50:08 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 14 Dec 2017 09:50:10 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 14 Dec 2017 09:50:11 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:12 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 14 Dec 2017 09:50:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Thu, 14 Dec 2017 09:50:14 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Sat, 21 Jul 2018 09:32:14 GMT
ENV PHP_VERSION=7.2.8
# Sat, 21 Jul 2018 09:32:15 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.8.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.8.tar.xz.asc/from/this/mirror
# Sat, 21 Jul 2018 09:32:16 GMT
ENV PHP_SHA256=53ba0708be8a7db44256e3ae9fcecc91b811e5b5119e6080c951ffe7910ffb0f PHP_MD5=
# Sat, 21 Jul 2018 09:32:30 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		wget 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		command -v gpgconf > /dev/null && gpgconf --kill all; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 21 Jul 2018 09:32:31 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 21 Jul 2018 09:36:39 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:36:43 GMT
RUN docker-php-ext-enable sodium
# Sat, 21 Jul 2018 09:36:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 21 Jul 2018 09:36:48 GMT
CMD ["php" "-a"]
# Sat, 21 Jul 2018 13:10:08 GMT
RUN apk --no-cache add git subversion openssh mercurial tini bash patch
# Sat, 21 Jul 2018 13:10:13 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 21 Jul 2018 13:10:59 GMT
RUN apk add --no-cache --virtual .build-deps zlib-dev  && docker-php-ext-install zip  && runDeps="$(     scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions     | tr ',' '\n'     | sort -u     | awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }'     )"  && apk add --virtual .composer-phpext-rundeps $runDeps  && apk del .build-deps
# Sat, 21 Jul 2018 13:11:03 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 21 Jul 2018 13:11:04 GMT
ENV COMPOSER_HOME=/tmp
# Thu, 09 Aug 2018 08:16:29 GMT
ENV COMPOSER_VERSION=1.7.1
# Thu, 09 Aug 2018 08:16:35 GMT
RUN curl --silent --fail --location --retry 3 --output /tmp/installer.php --url https://raw.githubusercontent.com/composer/getcomposer.org/b107d959a5924af895807021fcef4ffec5a76aa9/web/installer  && php -r "     \$signature = '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && composer --ansi --version --no-interaction  && rm -rf /tmp/* /tmp/.htaccess
# Thu, 09 Aug 2018 08:16:37 GMT
COPY file:295943a303e8f27de4302b6aa3687bce4b1d1392335efaaab9ecd37bec5ab4c5 in /docker-entrypoint.sh 
# Thu, 09 Aug 2018 08:16:38 GMT
WORKDIR /app
# Thu, 09 Aug 2018 08:16:39 GMT
ENTRYPOINT ["/bin/sh" "/docker-entrypoint.sh"]
# Thu, 09 Aug 2018 08:16:40 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bcb39b8c697dd02c12a952dcc63b609d7c7bf9d66e93e5e4913d2eeeaf894d3`  
		Last Modified: Thu, 14 Dec 2017 10:14:08 GMT  
		Size: 1.3 MB (1256438 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a484a708d295b3464c467d2a9bd8343046d4f4905c5776958832b3f6754c2f6`  
		Last Modified: Thu, 14 Dec 2017 10:14:07 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b360613871987866ea7defe9eb40283e850669f1475e97eb519e25f1f522df28`  
		Last Modified: Thu, 14 Dec 2017 10:14:05 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d99f731b990d2a294f320a84b14121e4e780b51ad02cfa139d6eb98cc07be49`  
		Last Modified: Sat, 21 Jul 2018 11:43:23 GMT  
		Size: 12.2 MB (12172924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae20c5e557170e7ef350bc75beebd7fbc2c16ab587cd116170f7fceefdfa9e1a`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:655202fd686ff06dfd119a0dbb980504002d0c0a4c6bec1e1101d45dbba37fef`  
		Last Modified: Sat, 21 Jul 2018 11:43:29 GMT  
		Size: 17.1 MB (17060912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92f832a9b29c8a33de4456a239a95f1f18b81134a215f4ab342b95dea4a28089`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23793d8390f3178b5bd3663a3bf7caa499108ad9360472cf6905f2c6cc5e5678`  
		Last Modified: Sat, 21 Jul 2018 11:43:21 GMT  
		Size: 70.9 KB (70874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c79c27e94614d8417bec4c976c4cb632c4b68077418a320c024a4ecc4efd3eb`  
		Last Modified: Sat, 21 Jul 2018 13:12:52 GMT  
		Size: 26.1 MB (26131964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d48aced734ec97b3d1ce545029ad53e00d50d6e2f482dd0991bb8e035402de2`  
		Last Modified: Sat, 21 Jul 2018 13:12:44 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61e2c3735fd09a13af5db256265c195ba044c789e511936f5a819dbe8e4e098e`  
		Last Modified: Sat, 21 Jul 2018 13:12:42 GMT  
		Size: 227.3 KB (227292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98555166c596da13aa1972ec6d1714174d24bb23b22f372a7f6a739436ccde0b`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 477.6 KB (477590 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1fdf7b4b2db397e5057a7fe99b9bd37aa853dc6dafc02248da0e8c344a28ecb`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a9f064a9b5cc2ec9d54cfc0a012b3ec766bcac43d8f0842d985391ab04612e8`  
		Last Modified: Thu, 09 Aug 2018 08:17:00 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
