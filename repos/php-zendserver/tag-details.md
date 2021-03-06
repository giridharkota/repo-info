<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `php-zendserver`

-	[`php-zendserver:2018.0`](#php-zendserver20180)
-	[`php-zendserver:5.6`](#php-zendserver56)
-	[`php-zendserver:8.5`](#php-zendserver85)
-	[`php-zendserver:8.5-php5.6`](#php-zendserver85-php56)
-	[`php-zendserver:9.1`](#php-zendserver91)
-	[`php-zendserver:latest`](#php-zendserverlatest)

## `php-zendserver:2018.0`

```console
$ docker pull php-zendserver@sha256:22dc54c36876f8d70d3ae4f865081839411373b350d435fa5f4d0d8c1a27fdfe
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `php-zendserver:2018.0` - linux; amd64

```console
$ docker pull php-zendserver@sha256:c1b8c9a209be647fdf1431c4fd5afc0f9fe91558f85aec7737a670d9bd0053c0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **347.2 MB (347194959 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f3976ca01ea0b0952a8ad38f6232685d9218b7308fa2b4ee79e47ba01265ce06`
-	Default Command: `["\/usr\/local\/bin\/run"]`

```dockerfile
# Thu, 26 Jul 2018 22:23:08 GMT
ADD file:204fb7ccb19ff7e863331131138621ff4d22720b3718e8f296902cc7d4f635b5 in / 
# Thu, 26 Jul 2018 22:23:09 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 26 Jul 2018 22:23:09 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 26 Jul 2018 22:23:10 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 26 Jul 2018 22:23:11 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 26 Jul 2018 22:23:11 GMT
CMD ["/bin/bash"]
# Fri, 27 Jul 2018 00:08:29 GMT
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-key 799058698E65316A2E7A4FF42EAE1437F7D2C623     && echo "deb http://repos.zend.com/zend-server/2018.0/deb_apache2.4 server non-free" >> /etc/apt/sources.list.d/zend-server.list     && apt-get update     && apt-get install -y       libmysqlclient20       unzip       git       curl       net-tools       zend-server-php-7.2=2018.0.0+b464     && rm -rf /var/lib/apt/lists/*     && /usr/local/zend/bin/zendctl.sh stop
# Fri, 27 Jul 2018 00:08:30 GMT
COPY file:600eecb7e31561caebcef5617a4923b3065c52e6ae17fcce39ffdcc8ca6c41db in /etc/ 
# Fri, 27 Jul 2018 00:08:30 GMT
COPY file:82de006e31874ac4e03685b3e87e988446f42138aaaf0fc5faad9cddb48040ba in /etc/apache2/conf-available 
# Fri, 27 Jul 2018 00:08:31 GMT
RUN /usr/sbin/a2enconf drop-http-proxy-header      && /usr/sbin/a2enmod headers
# Fri, 27 Jul 2018 00:08:32 GMT
ENV ZS_INIT_VERSION=0.3
# Fri, 27 Jul 2018 00:08:32 GMT
ENV ZS_INIT_SHA256=e8d441d8503808e9fc0fafc762b2cb80d4a6e68b94fede0fe41efdeac10800cb
# Fri, 27 Jul 2018 00:08:33 GMT
RUN curl -fSL -o zs-init.tar.gz "http://repos.zend.com/zs-init/zs-init-docker-${ZS_INIT_VERSION}.tar.gz"     && echo "${ZS_INIT_SHA256} *zs-init.tar.gz" | sha256sum -c -     && mkdir /usr/local/zs-init     && tar xzf zs-init.tar.gz --strip-components=1 -C /usr/local/zs-init     && rm zs-init.tar.gz
# Fri, 27 Jul 2018 00:08:33 GMT
WORKDIR /usr/local/zs-init
# Fri, 27 Jul 2018 00:09:05 GMT
RUN /usr/local/zend/bin/php /usr/local/zend/bin/composer.phar self-update && /usr/local/zend/bin/php /usr/local/zend/bin/composer.phar update
# Fri, 27 Jul 2018 00:09:23 GMT
COPY dir:15e41e43c0ea26254e53363ef64d6f20b76b254a017ddeac1bce0422b2cdaa9a in /usr/local/bin 
# Fri, 27 Jul 2018 00:09:23 GMT
COPY dir:b14dbc48195e4d5367d3aea2ed0fb26985bacb8d8229d24961363db2e2edf8f0 in /usr/local/zend/var/plugins/ 
# Fri, 27 Jul 2018 00:09:24 GMT
RUN rm /var/www/html/index.html
# Fri, 27 Jul 2018 00:09:25 GMT
COPY dir:9f1a7f23dfcf85f3c7148d98ae7914654fe8acfc4e4651f3a08427c09af24198 in /var/www/html 
# Fri, 27 Jul 2018 00:09:25 GMT
EXPOSE 80/tcp
# Fri, 27 Jul 2018 00:09:25 GMT
EXPOSE 443/tcp
# Fri, 27 Jul 2018 00:09:25 GMT
EXPOSE 10081/tcp
# Fri, 27 Jul 2018 00:09:26 GMT
EXPOSE 10082/tcp
# Fri, 27 Jul 2018 00:09:27 GMT
WORKDIR /var/www/html
# Fri, 27 Jul 2018 00:09:27 GMT
CMD ["/usr/local/bin/run"]
```

-	Layers:
	-	`sha256:8ee29e426c26c79e7ba03ccc8bbc7fe99db00ffcbccb679d9c643b5546d8dc8a`  
		Last Modified: Thu, 26 Jul 2018 22:27:22 GMT  
		Size: 43.2 MB (43228646 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e83b260b73b908ebabde46b72fc5790bf4f029b53acbbfe35da8ff8fba795ac`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e26b65fd1143ee4f9b7b6b958aeafdb996172d10b723f0bba24335a8f7ae692c`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 618.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40dca07f8222e24aab97f026444d66a7604e4ae2b708cf079ff67a90c42efa60`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b420ae9e10b3f6a74f527914bc3c766b128435a62eca1061f41167205d5b0230`  
		Last Modified: Thu, 26 Jul 2018 22:26:54 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8497cfbaf872bab1de35f30b459e2e1fcc60d613cd22aa96d909d41a491dcea5`  
		Last Modified: Fri, 27 Jul 2018 00:14:02 GMT  
		Size: 287.6 MB (287580521 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b65b83a9fd93a2d731ea1651b8e35425536172eddee1c1026d27c47a9433fe94`  
		Last Modified: Fri, 27 Jul 2018 00:12:26 GMT  
		Size: 220.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0ffd0fada9766a416a4fae55b6ef2cdf0cfb5412cbda152058f5f3b3fa80306`  
		Last Modified: Fri, 27 Jul 2018 00:12:25 GMT  
		Size: 260.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1b836e1ecb7d842d2b909728d0888c2ddc738db7d3e84dce2c7d7657ef374e8`  
		Last Modified: Fri, 27 Jul 2018 00:12:24 GMT  
		Size: 407.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ebecda9572edfec138f28a13d780bc4a74f1c44c8cd19422877a93571333906`  
		Last Modified: Fri, 27 Jul 2018 00:12:25 GMT  
		Size: 18.8 KB (18828 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a0831dabec74976bff96de7e74f884bb1795f33bc44005b1a7d5245c59cb240`  
		Last Modified: Fri, 27 Jul 2018 00:12:28 GMT  
		Size: 16.3 MB (16345390 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47f9292def208cb82d39f359e69752de61747a2b5450b0152115cd201c831481`  
		Last Modified: Fri, 27 Jul 2018 00:12:22 GMT  
		Size: 14.2 KB (14250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:035efdb89f13e495311cd543b6772e22bbc1eefbaeb20addb84722b9a8f5f8e2`  
		Last Modified: Fri, 27 Jul 2018 00:12:22 GMT  
		Size: 2.5 KB (2532 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f56919170f07126986f47fbc5b46de840eea88e9f3c02b9d0abeef5a28ea599e`  
		Last Modified: Fri, 27 Jul 2018 00:12:23 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e1b07e36ec6d728f4a41ba00dfd97517c3d177f751a20869a758da2384ea4cb`  
		Last Modified: Fri, 27 Jul 2018 00:12:22 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `php-zendserver:5.6`

```console
$ docker pull php-zendserver@sha256:9d85be3edf24760c054bd8af715feb6973383266cd9fddc22e0e3a0a78ad8180
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `php-zendserver:5.6` - linux; amd64

```console
$ docker pull php-zendserver@sha256:6bac7d38cdea9cc47b549facc1ae278d10f34ffe0218c2ea94beb92f594012be
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **339.8 MB (339778443 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d7aec1e183533b76874102a8e1701b868c736186ad6d3128445b26ceb042f775`
-	Default Command: `["\/usr\/local\/bin\/run"]`

```dockerfile
# Tue, 17 Jul 2018 00:53:22 GMT
ADD file:2b307231ea5854129fb2b708dc49d44d30c66023186d861778defb768aa3a8a8 in / 
# Tue, 17 Jul 2018 00:53:24 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 17 Jul 2018 00:53:24 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 00:53:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 17 Jul 2018 00:53:26 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 17 Jul 2018 00:53:26 GMT
CMD ["/bin/bash"]
# Tue, 17 Jul 2018 10:24:45 GMT
RUN apt-key adv --keyserver pgp.mit.edu --recv-key 799058698E65316A2E7A4FF42EAE1437F7D2C623
# Tue, 17 Jul 2018 10:24:46 GMT
RUN echo "deb http://repos.zend.com/zend-server/8.5.10/deb_apache2.4 server non-free" >> /etc/apt/sources.list.d/zend-server.list
# Tue, 17 Jul 2018 10:26:53 GMT
RUN apt-get update && apt-get install -y curl libmysqlclient18 unzip git zend-server-php-5.6=8.5.10+b798 && /usr/local/zend/bin/zendctl.sh stop
# Tue, 17 Jul 2018 10:26:55 GMT
COPY file:600eecb7e31561caebcef5617a4923b3065c52e6ae17fcce39ffdcc8ca6c41db in /etc/ 
# Tue, 17 Jul 2018 10:26:56 GMT
COPY file:82de006e31874ac4e03685b3e87e988446f42138aaaf0fc5faad9cddb48040ba in /etc/apache2/conf-available 
# Tue, 17 Jul 2018 10:26:57 GMT
RUN /usr/sbin/a2enconf drop-http-proxy-header
# Tue, 17 Jul 2018 10:26:58 GMT
RUN /usr/sbin/a2enmod headers
# Tue, 17 Jul 2018 10:26:58 GMT
ENV ZS_INIT_VERSION=0.3
# Tue, 17 Jul 2018 10:26:58 GMT
ENV ZS_INIT_SHA256=e8d441d8503808e9fc0fafc762b2cb80d4a6e68b94fede0fe41efdeac10800cb
# Tue, 17 Jul 2018 10:26:59 GMT
RUN curl -fSL -o zs-init.tar.gz "http://repos.zend.com/zs-init/zs-init-docker-${ZS_INIT_VERSION}.tar.gz"     && echo "${ZS_INIT_SHA256} *zs-init.tar.gz" | sha256sum -c -     && mkdir /usr/local/zs-init     && tar xzf zs-init.tar.gz --strip-components=1 -C /usr/local/zs-init     && rm zs-init.tar.gz
# Tue, 17 Jul 2018 10:26:59 GMT
WORKDIR /usr/local/zs-init
# Tue, 17 Jul 2018 10:27:03 GMT
RUN /usr/local/zend/bin/php -r "readfile('https://getcomposer.org/installer');" | /usr/local/zend/bin/php
# Tue, 17 Jul 2018 10:28:01 GMT
RUN /usr/local/zend/bin/php composer.phar update
# Tue, 17 Jul 2018 10:28:01 GMT
COPY dir:6174d7fdcd8142a1b143e80efd2994e57dd5d7610a8fbfee3a7288ddf495dfdf in /usr/local/bin 
# Tue, 17 Jul 2018 10:28:01 GMT
COPY dir:b14dbc48195e4d5367d3aea2ed0fb26985bacb8d8229d24961363db2e2edf8f0 in /usr/local/zend/var/plugins/ 
# Tue, 17 Jul 2018 10:28:02 GMT
RUN rm /var/www/html/index.html
# Tue, 17 Jul 2018 10:28:02 GMT
COPY dir:9f1a7f23dfcf85f3c7148d98ae7914654fe8acfc4e4651f3a08427c09af24198 in /var/www/html 
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 80/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 443/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 10081/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 10082/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
WORKDIR /var/www/html
# Tue, 17 Jul 2018 10:28:04 GMT
CMD ["/usr/local/bin/run"]
```

-	Layers:
	-	`sha256:8284e13a281d55cc734a66ada0b6cabef2447ce16e91ce96317eca132253f734`  
		Last Modified: Tue, 17 Jul 2018 00:58:36 GMT  
		Size: 67.1 MB (67127095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26e1916a92974ed667a04ce36771ef2599e58e2e3b118375e19a8af98c6fa3b2`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 72.6 KB (72649 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4102fc66d4abcb83d0739b402e2fd6e9a884d75ad9cbada70bc9286d58d97abf`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 364.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cf2b01777b2f9a1c015cc2b7c39b9916de816806c3eee2d1b6cd63757868451`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f7a2d5e04ed4e9237521229a3e7837dc552b4e1157b79c02c2fecbc14003032`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5466506e8f092a493529389a36a1f85b2c045a95e3f42b28db40b4241737cf26`  
		Last Modified: Tue, 17 Jul 2018 10:35:07 GMT  
		Size: 13.1 KB (13058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b948ac0cf733d39cddb9a5aaa13000286105fc31afa6ba7a1087bb0ab92951b5`  
		Last Modified: Tue, 17 Jul 2018 10:35:06 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca05bb8677e32d64f15b395c97cec087407f26483fe92bcb10b9f2b59003221a`  
		Last Modified: Tue, 17 Jul 2018 10:36:11 GMT  
		Size: 256.7 MB (256741383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70e2e05af8560dc24becb0f5cb344809809c438b787a4cfc7ab0705f1e26d40e`  
		Last Modified: Tue, 17 Jul 2018 10:35:05 GMT  
		Size: 220.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3541b91a287f0fe6d019d47567721fbf58e3c2168decd78a61dfa81ae27ccc03`  
		Last Modified: Tue, 17 Jul 2018 10:35:04 GMT  
		Size: 262.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c03b336f6cfff4849c1692d0e21d1a9716e21b0b1720a8aa6ca69201b2223a47`  
		Last Modified: Tue, 17 Jul 2018 10:35:03 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b651fcb25a3f41a8108c48511da4a8163c8ad54e595b10f414a7d24580cae48`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 305.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60c8a4d062bffe77409c49dd917055b79157dbfe996148dc8cafd0e5a5bf7724`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 18.8 KB (18834 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53bb3e953464d7a99a359ff5165aa5b7aa2cd0bcc1d39d951373d94d7e452429`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 478.0 KB (477979 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f822580382c4382d6db94b263ca7f698512edd0e23359775643ce8329acab991`  
		Last Modified: Tue, 17 Jul 2018 10:35:05 GMT  
		Size: 15.3 MB (15307416 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1afbacfff012fc9484c5db98a1b9366da333f3836b670eed55e5133eee0aa1d5`  
		Last Modified: Tue, 17 Jul 2018 10:35:00 GMT  
		Size: 13.4 KB (13359 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f011806853249f805a198d39946aef7327cae74676ccc8df929fd2b81629646d`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 2.5 KB (2539 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9e41452a2a668c02ea2d40ff76e30c681e6f272500c2d6dd17a5f19c18ae710`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ec390385bb3d614e45a4d7b745c1c56adf5c7ca0287fe3af0c9c88f5edd3aeb`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `php-zendserver:8.5`

```console
$ docker pull php-zendserver@sha256:9d85be3edf24760c054bd8af715feb6973383266cd9fddc22e0e3a0a78ad8180
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `php-zendserver:8.5` - linux; amd64

```console
$ docker pull php-zendserver@sha256:6bac7d38cdea9cc47b549facc1ae278d10f34ffe0218c2ea94beb92f594012be
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **339.8 MB (339778443 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d7aec1e183533b76874102a8e1701b868c736186ad6d3128445b26ceb042f775`
-	Default Command: `["\/usr\/local\/bin\/run"]`

```dockerfile
# Tue, 17 Jul 2018 00:53:22 GMT
ADD file:2b307231ea5854129fb2b708dc49d44d30c66023186d861778defb768aa3a8a8 in / 
# Tue, 17 Jul 2018 00:53:24 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 17 Jul 2018 00:53:24 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 00:53:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 17 Jul 2018 00:53:26 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 17 Jul 2018 00:53:26 GMT
CMD ["/bin/bash"]
# Tue, 17 Jul 2018 10:24:45 GMT
RUN apt-key adv --keyserver pgp.mit.edu --recv-key 799058698E65316A2E7A4FF42EAE1437F7D2C623
# Tue, 17 Jul 2018 10:24:46 GMT
RUN echo "deb http://repos.zend.com/zend-server/8.5.10/deb_apache2.4 server non-free" >> /etc/apt/sources.list.d/zend-server.list
# Tue, 17 Jul 2018 10:26:53 GMT
RUN apt-get update && apt-get install -y curl libmysqlclient18 unzip git zend-server-php-5.6=8.5.10+b798 && /usr/local/zend/bin/zendctl.sh stop
# Tue, 17 Jul 2018 10:26:55 GMT
COPY file:600eecb7e31561caebcef5617a4923b3065c52e6ae17fcce39ffdcc8ca6c41db in /etc/ 
# Tue, 17 Jul 2018 10:26:56 GMT
COPY file:82de006e31874ac4e03685b3e87e988446f42138aaaf0fc5faad9cddb48040ba in /etc/apache2/conf-available 
# Tue, 17 Jul 2018 10:26:57 GMT
RUN /usr/sbin/a2enconf drop-http-proxy-header
# Tue, 17 Jul 2018 10:26:58 GMT
RUN /usr/sbin/a2enmod headers
# Tue, 17 Jul 2018 10:26:58 GMT
ENV ZS_INIT_VERSION=0.3
# Tue, 17 Jul 2018 10:26:58 GMT
ENV ZS_INIT_SHA256=e8d441d8503808e9fc0fafc762b2cb80d4a6e68b94fede0fe41efdeac10800cb
# Tue, 17 Jul 2018 10:26:59 GMT
RUN curl -fSL -o zs-init.tar.gz "http://repos.zend.com/zs-init/zs-init-docker-${ZS_INIT_VERSION}.tar.gz"     && echo "${ZS_INIT_SHA256} *zs-init.tar.gz" | sha256sum -c -     && mkdir /usr/local/zs-init     && tar xzf zs-init.tar.gz --strip-components=1 -C /usr/local/zs-init     && rm zs-init.tar.gz
# Tue, 17 Jul 2018 10:26:59 GMT
WORKDIR /usr/local/zs-init
# Tue, 17 Jul 2018 10:27:03 GMT
RUN /usr/local/zend/bin/php -r "readfile('https://getcomposer.org/installer');" | /usr/local/zend/bin/php
# Tue, 17 Jul 2018 10:28:01 GMT
RUN /usr/local/zend/bin/php composer.phar update
# Tue, 17 Jul 2018 10:28:01 GMT
COPY dir:6174d7fdcd8142a1b143e80efd2994e57dd5d7610a8fbfee3a7288ddf495dfdf in /usr/local/bin 
# Tue, 17 Jul 2018 10:28:01 GMT
COPY dir:b14dbc48195e4d5367d3aea2ed0fb26985bacb8d8229d24961363db2e2edf8f0 in /usr/local/zend/var/plugins/ 
# Tue, 17 Jul 2018 10:28:02 GMT
RUN rm /var/www/html/index.html
# Tue, 17 Jul 2018 10:28:02 GMT
COPY dir:9f1a7f23dfcf85f3c7148d98ae7914654fe8acfc4e4651f3a08427c09af24198 in /var/www/html 
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 80/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 443/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 10081/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 10082/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
WORKDIR /var/www/html
# Tue, 17 Jul 2018 10:28:04 GMT
CMD ["/usr/local/bin/run"]
```

-	Layers:
	-	`sha256:8284e13a281d55cc734a66ada0b6cabef2447ce16e91ce96317eca132253f734`  
		Last Modified: Tue, 17 Jul 2018 00:58:36 GMT  
		Size: 67.1 MB (67127095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26e1916a92974ed667a04ce36771ef2599e58e2e3b118375e19a8af98c6fa3b2`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 72.6 KB (72649 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4102fc66d4abcb83d0739b402e2fd6e9a884d75ad9cbada70bc9286d58d97abf`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 364.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cf2b01777b2f9a1c015cc2b7c39b9916de816806c3eee2d1b6cd63757868451`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f7a2d5e04ed4e9237521229a3e7837dc552b4e1157b79c02c2fecbc14003032`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5466506e8f092a493529389a36a1f85b2c045a95e3f42b28db40b4241737cf26`  
		Last Modified: Tue, 17 Jul 2018 10:35:07 GMT  
		Size: 13.1 KB (13058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b948ac0cf733d39cddb9a5aaa13000286105fc31afa6ba7a1087bb0ab92951b5`  
		Last Modified: Tue, 17 Jul 2018 10:35:06 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca05bb8677e32d64f15b395c97cec087407f26483fe92bcb10b9f2b59003221a`  
		Last Modified: Tue, 17 Jul 2018 10:36:11 GMT  
		Size: 256.7 MB (256741383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70e2e05af8560dc24becb0f5cb344809809c438b787a4cfc7ab0705f1e26d40e`  
		Last Modified: Tue, 17 Jul 2018 10:35:05 GMT  
		Size: 220.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3541b91a287f0fe6d019d47567721fbf58e3c2168decd78a61dfa81ae27ccc03`  
		Last Modified: Tue, 17 Jul 2018 10:35:04 GMT  
		Size: 262.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c03b336f6cfff4849c1692d0e21d1a9716e21b0b1720a8aa6ca69201b2223a47`  
		Last Modified: Tue, 17 Jul 2018 10:35:03 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b651fcb25a3f41a8108c48511da4a8163c8ad54e595b10f414a7d24580cae48`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 305.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60c8a4d062bffe77409c49dd917055b79157dbfe996148dc8cafd0e5a5bf7724`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 18.8 KB (18834 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53bb3e953464d7a99a359ff5165aa5b7aa2cd0bcc1d39d951373d94d7e452429`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 478.0 KB (477979 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f822580382c4382d6db94b263ca7f698512edd0e23359775643ce8329acab991`  
		Last Modified: Tue, 17 Jul 2018 10:35:05 GMT  
		Size: 15.3 MB (15307416 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1afbacfff012fc9484c5db98a1b9366da333f3836b670eed55e5133eee0aa1d5`  
		Last Modified: Tue, 17 Jul 2018 10:35:00 GMT  
		Size: 13.4 KB (13359 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f011806853249f805a198d39946aef7327cae74676ccc8df929fd2b81629646d`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 2.5 KB (2539 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9e41452a2a668c02ea2d40ff76e30c681e6f272500c2d6dd17a5f19c18ae710`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ec390385bb3d614e45a4d7b745c1c56adf5c7ca0287fe3af0c9c88f5edd3aeb`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `php-zendserver:8.5-php5.6`

```console
$ docker pull php-zendserver@sha256:9d85be3edf24760c054bd8af715feb6973383266cd9fddc22e0e3a0a78ad8180
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `php-zendserver:8.5-php5.6` - linux; amd64

```console
$ docker pull php-zendserver@sha256:6bac7d38cdea9cc47b549facc1ae278d10f34ffe0218c2ea94beb92f594012be
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **339.8 MB (339778443 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d7aec1e183533b76874102a8e1701b868c736186ad6d3128445b26ceb042f775`
-	Default Command: `["\/usr\/local\/bin\/run"]`

```dockerfile
# Tue, 17 Jul 2018 00:53:22 GMT
ADD file:2b307231ea5854129fb2b708dc49d44d30c66023186d861778defb768aa3a8a8 in / 
# Tue, 17 Jul 2018 00:53:24 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 17 Jul 2018 00:53:24 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 00:53:25 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 17 Jul 2018 00:53:26 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 17 Jul 2018 00:53:26 GMT
CMD ["/bin/bash"]
# Tue, 17 Jul 2018 10:24:45 GMT
RUN apt-key adv --keyserver pgp.mit.edu --recv-key 799058698E65316A2E7A4FF42EAE1437F7D2C623
# Tue, 17 Jul 2018 10:24:46 GMT
RUN echo "deb http://repos.zend.com/zend-server/8.5.10/deb_apache2.4 server non-free" >> /etc/apt/sources.list.d/zend-server.list
# Tue, 17 Jul 2018 10:26:53 GMT
RUN apt-get update && apt-get install -y curl libmysqlclient18 unzip git zend-server-php-5.6=8.5.10+b798 && /usr/local/zend/bin/zendctl.sh stop
# Tue, 17 Jul 2018 10:26:55 GMT
COPY file:600eecb7e31561caebcef5617a4923b3065c52e6ae17fcce39ffdcc8ca6c41db in /etc/ 
# Tue, 17 Jul 2018 10:26:56 GMT
COPY file:82de006e31874ac4e03685b3e87e988446f42138aaaf0fc5faad9cddb48040ba in /etc/apache2/conf-available 
# Tue, 17 Jul 2018 10:26:57 GMT
RUN /usr/sbin/a2enconf drop-http-proxy-header
# Tue, 17 Jul 2018 10:26:58 GMT
RUN /usr/sbin/a2enmod headers
# Tue, 17 Jul 2018 10:26:58 GMT
ENV ZS_INIT_VERSION=0.3
# Tue, 17 Jul 2018 10:26:58 GMT
ENV ZS_INIT_SHA256=e8d441d8503808e9fc0fafc762b2cb80d4a6e68b94fede0fe41efdeac10800cb
# Tue, 17 Jul 2018 10:26:59 GMT
RUN curl -fSL -o zs-init.tar.gz "http://repos.zend.com/zs-init/zs-init-docker-${ZS_INIT_VERSION}.tar.gz"     && echo "${ZS_INIT_SHA256} *zs-init.tar.gz" | sha256sum -c -     && mkdir /usr/local/zs-init     && tar xzf zs-init.tar.gz --strip-components=1 -C /usr/local/zs-init     && rm zs-init.tar.gz
# Tue, 17 Jul 2018 10:26:59 GMT
WORKDIR /usr/local/zs-init
# Tue, 17 Jul 2018 10:27:03 GMT
RUN /usr/local/zend/bin/php -r "readfile('https://getcomposer.org/installer');" | /usr/local/zend/bin/php
# Tue, 17 Jul 2018 10:28:01 GMT
RUN /usr/local/zend/bin/php composer.phar update
# Tue, 17 Jul 2018 10:28:01 GMT
COPY dir:6174d7fdcd8142a1b143e80efd2994e57dd5d7610a8fbfee3a7288ddf495dfdf in /usr/local/bin 
# Tue, 17 Jul 2018 10:28:01 GMT
COPY dir:b14dbc48195e4d5367d3aea2ed0fb26985bacb8d8229d24961363db2e2edf8f0 in /usr/local/zend/var/plugins/ 
# Tue, 17 Jul 2018 10:28:02 GMT
RUN rm /var/www/html/index.html
# Tue, 17 Jul 2018 10:28:02 GMT
COPY dir:9f1a7f23dfcf85f3c7148d98ae7914654fe8acfc4e4651f3a08427c09af24198 in /var/www/html 
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 80/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 443/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 10081/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
EXPOSE 10082/tcp
# Tue, 17 Jul 2018 10:28:03 GMT
WORKDIR /var/www/html
# Tue, 17 Jul 2018 10:28:04 GMT
CMD ["/usr/local/bin/run"]
```

-	Layers:
	-	`sha256:8284e13a281d55cc734a66ada0b6cabef2447ce16e91ce96317eca132253f734`  
		Last Modified: Tue, 17 Jul 2018 00:58:36 GMT  
		Size: 67.1 MB (67127095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26e1916a92974ed667a04ce36771ef2599e58e2e3b118375e19a8af98c6fa3b2`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 72.6 KB (72649 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4102fc66d4abcb83d0739b402e2fd6e9a884d75ad9cbada70bc9286d58d97abf`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 364.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cf2b01777b2f9a1c015cc2b7c39b9916de816806c3eee2d1b6cd63757868451`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f7a2d5e04ed4e9237521229a3e7837dc552b4e1157b79c02c2fecbc14003032`  
		Last Modified: Tue, 17 Jul 2018 00:58:11 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5466506e8f092a493529389a36a1f85b2c045a95e3f42b28db40b4241737cf26`  
		Last Modified: Tue, 17 Jul 2018 10:35:07 GMT  
		Size: 13.1 KB (13058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b948ac0cf733d39cddb9a5aaa13000286105fc31afa6ba7a1087bb0ab92951b5`  
		Last Modified: Tue, 17 Jul 2018 10:35:06 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca05bb8677e32d64f15b395c97cec087407f26483fe92bcb10b9f2b59003221a`  
		Last Modified: Tue, 17 Jul 2018 10:36:11 GMT  
		Size: 256.7 MB (256741383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70e2e05af8560dc24becb0f5cb344809809c438b787a4cfc7ab0705f1e26d40e`  
		Last Modified: Tue, 17 Jul 2018 10:35:05 GMT  
		Size: 220.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3541b91a287f0fe6d019d47567721fbf58e3c2168decd78a61dfa81ae27ccc03`  
		Last Modified: Tue, 17 Jul 2018 10:35:04 GMT  
		Size: 262.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c03b336f6cfff4849c1692d0e21d1a9716e21b0b1720a8aa6ca69201b2223a47`  
		Last Modified: Tue, 17 Jul 2018 10:35:03 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b651fcb25a3f41a8108c48511da4a8163c8ad54e595b10f414a7d24580cae48`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 305.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60c8a4d062bffe77409c49dd917055b79157dbfe996148dc8cafd0e5a5bf7724`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 18.8 KB (18834 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53bb3e953464d7a99a359ff5165aa5b7aa2cd0bcc1d39d951373d94d7e452429`  
		Last Modified: Tue, 17 Jul 2018 10:35:02 GMT  
		Size: 478.0 KB (477979 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f822580382c4382d6db94b263ca7f698512edd0e23359775643ce8329acab991`  
		Last Modified: Tue, 17 Jul 2018 10:35:05 GMT  
		Size: 15.3 MB (15307416 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1afbacfff012fc9484c5db98a1b9366da333f3836b670eed55e5133eee0aa1d5`  
		Last Modified: Tue, 17 Jul 2018 10:35:00 GMT  
		Size: 13.4 KB (13359 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f011806853249f805a198d39946aef7327cae74676ccc8df929fd2b81629646d`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 2.5 KB (2539 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9e41452a2a668c02ea2d40ff76e30c681e6f272500c2d6dd17a5f19c18ae710`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ec390385bb3d614e45a4d7b745c1c56adf5c7ca0287fe3af0c9c88f5edd3aeb`  
		Last Modified: Tue, 17 Jul 2018 10:34:59 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `php-zendserver:9.1`

```console
$ docker pull php-zendserver@sha256:119518057a318c5e271defad16a00d6de1cce75247fd08e509b06f86df76f4c5
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `php-zendserver:9.1` - linux; amd64

```console
$ docker pull php-zendserver@sha256:cac0cc2c6c4a65e343037b8499580354b86860ed290625b446bd38f83f997878
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **406.9 MB (406864587 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc6aa4bc8281a6cf1cc32e4b94666b3f273704d4abc705b458f7bb8b515f9ab3`
-	Default Command: `["\/usr\/local\/bin\/run"]`

```dockerfile
# Thu, 26 Jul 2018 22:23:08 GMT
ADD file:204fb7ccb19ff7e863331131138621ff4d22720b3718e8f296902cc7d4f635b5 in / 
# Thu, 26 Jul 2018 22:23:09 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 26 Jul 2018 22:23:09 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 26 Jul 2018 22:23:10 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 26 Jul 2018 22:23:11 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 26 Jul 2018 22:23:11 GMT
CMD ["/bin/bash"]
# Fri, 27 Jul 2018 00:04:45 GMT
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-key 799058698E65316A2E7A4FF42EAE1437F7D2C623     && echo "deb http://repos.zend.com/zend-server/9.1/deb_apache2.4 server non-free" >> /etc/apt/sources.list.d/zend-server.list     && apt-get update     && apt-get install -y       libmysqlclient20       unzip       git       curl       net-tools       zend-server-php-7.1=9.1.4+b170     && rm -rf /var/lib/apt/lists/*     && /usr/local/zend/bin/zendctl.sh stop
# Fri, 27 Jul 2018 00:04:46 GMT
COPY file:600eecb7e31561caebcef5617a4923b3065c52e6ae17fcce39ffdcc8ca6c41db in /etc/ 
# Fri, 27 Jul 2018 00:05:03 GMT
COPY file:82de006e31874ac4e03685b3e87e988446f42138aaaf0fc5faad9cddb48040ba in /etc/apache2/conf-available 
# Fri, 27 Jul 2018 00:05:04 GMT
RUN /usr/sbin/a2enconf drop-http-proxy-header      && /usr/sbin/a2enmod headers
# Fri, 27 Jul 2018 00:05:04 GMT
ENV ZS_INIT_VERSION=0.3
# Fri, 27 Jul 2018 00:05:05 GMT
ENV ZS_INIT_SHA256=e8d441d8503808e9fc0fafc762b2cb80d4a6e68b94fede0fe41efdeac10800cb
# Fri, 27 Jul 2018 00:05:06 GMT
RUN curl -fSL -o zs-init.tar.gz "http://repos.zend.com/zs-init/zs-init-docker-${ZS_INIT_VERSION}.tar.gz"     && echo "${ZS_INIT_SHA256} *zs-init.tar.gz" | sha256sum -c -     && mkdir /usr/local/zs-init     && tar xzf zs-init.tar.gz --strip-components=1 -C /usr/local/zs-init     && rm zs-init.tar.gz
# Fri, 27 Jul 2018 00:05:06 GMT
WORKDIR /usr/local/zs-init
# Fri, 27 Jul 2018 00:05:40 GMT
RUN /usr/local/zend/bin/php -r "readfile('https://getcomposer.org/installer');" | /usr/local/zend/bin/php     && /usr/local/zend/bin/php composer.phar self-update && /usr/local/zend/bin/php composer.phar update
# Fri, 27 Jul 2018 00:05:56 GMT
COPY dir:87b268799bdfc4187e75754e18df8466bf3634663b9193cbf64ee0a291e978ab in /usr/local/bin 
# Fri, 27 Jul 2018 00:05:56 GMT
COPY dir:b14dbc48195e4d5367d3aea2ed0fb26985bacb8d8229d24961363db2e2edf8f0 in /usr/local/zend/var/plugins/ 
# Fri, 27 Jul 2018 00:05:58 GMT
RUN rm /var/www/html/index.html
# Fri, 27 Jul 2018 00:05:58 GMT
COPY dir:9f1a7f23dfcf85f3c7148d98ae7914654fe8acfc4e4651f3a08427c09af24198 in /var/www/html 
# Fri, 27 Jul 2018 00:05:58 GMT
EXPOSE 80/tcp
# Fri, 27 Jul 2018 00:05:59 GMT
EXPOSE 443/tcp
# Fri, 27 Jul 2018 00:05:59 GMT
EXPOSE 10081/tcp
# Fri, 27 Jul 2018 00:05:59 GMT
EXPOSE 10082/tcp
# Fri, 27 Jul 2018 00:06:00 GMT
WORKDIR /var/www/html
# Fri, 27 Jul 2018 00:06:00 GMT
CMD ["/usr/local/bin/run"]
```

-	Layers:
	-	`sha256:8ee29e426c26c79e7ba03ccc8bbc7fe99db00ffcbccb679d9c643b5546d8dc8a`  
		Last Modified: Thu, 26 Jul 2018 22:27:22 GMT  
		Size: 43.2 MB (43228646 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e83b260b73b908ebabde46b72fc5790bf4f029b53acbbfe35da8ff8fba795ac`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e26b65fd1143ee4f9b7b6b958aeafdb996172d10b723f0bba24335a8f7ae692c`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 618.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40dca07f8222e24aab97f026444d66a7604e4ae2b708cf079ff67a90c42efa60`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b420ae9e10b3f6a74f527914bc3c766b128435a62eca1061f41167205d5b0230`  
		Last Modified: Thu, 26 Jul 2018 22:26:54 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af29da731fa0944786f99092775081f09962e8647d1d9942270aa5c9e7638d94`  
		Last Modified: Fri, 27 Jul 2018 00:11:56 GMT  
		Size: 347.7 MB (347735226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53aba42604530ae8a17d43d3d82732e294448b7ac7e3e43339d5bcaeab4060eb`  
		Last Modified: Fri, 27 Jul 2018 00:10:08 GMT  
		Size: 217.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0605d48f2a0e4daad97664a820840b6777c2fac958d337d683edc77eb70d8f19`  
		Last Modified: Fri, 27 Jul 2018 00:10:08 GMT  
		Size: 261.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:328a5c2e68c4666c04e12864bfdafb3ab10524198d9295c9f173d228f598486f`  
		Last Modified: Fri, 27 Jul 2018 00:10:08 GMT  
		Size: 409.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbec9ec53d2a741209dacf24d2efd5ae1fb82d153e2bc3ed790863473e470d6c`  
		Last Modified: Fri, 27 Jul 2018 00:10:07 GMT  
		Size: 18.8 KB (18830 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14aeb1f7eb77169c302b22d4bbba7a3ea82d0dcc15b15e4818bdbc12d60268b8`  
		Last Modified: Fri, 27 Jul 2018 00:10:12 GMT  
		Size: 15.9 MB (15860257 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbf9484febc7bdc9736bd8648f2701d71a9f9256c055734ebf054a36f26991f0`  
		Last Modified: Fri, 27 Jul 2018 00:10:05 GMT  
		Size: 14.3 KB (14302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6dcc837bb85cabe6437c02595fb52133a7e73d835664d4be82b42cffa85be148`  
		Last Modified: Fri, 27 Jul 2018 00:10:05 GMT  
		Size: 2.5 KB (2534 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:710d38a34c858a16b41d65e1bcee21dcb89224601e3153598746b2f51cf88e57`  
		Last Modified: Fri, 27 Jul 2018 00:10:05 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f0696fe6686864aa51ed5784ad08189f2eb2a1036b453a9c3fb859f1bd59b1a`  
		Last Modified: Fri, 27 Jul 2018 00:10:05 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `php-zendserver:latest`

```console
$ docker pull php-zendserver@sha256:22dc54c36876f8d70d3ae4f865081839411373b350d435fa5f4d0d8c1a27fdfe
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `php-zendserver:latest` - linux; amd64

```console
$ docker pull php-zendserver@sha256:c1b8c9a209be647fdf1431c4fd5afc0f9fe91558f85aec7737a670d9bd0053c0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **347.2 MB (347194959 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f3976ca01ea0b0952a8ad38f6232685d9218b7308fa2b4ee79e47ba01265ce06`
-	Default Command: `["\/usr\/local\/bin\/run"]`

```dockerfile
# Thu, 26 Jul 2018 22:23:08 GMT
ADD file:204fb7ccb19ff7e863331131138621ff4d22720b3718e8f296902cc7d4f635b5 in / 
# Thu, 26 Jul 2018 22:23:09 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 26 Jul 2018 22:23:09 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 26 Jul 2018 22:23:10 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 26 Jul 2018 22:23:11 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 26 Jul 2018 22:23:11 GMT
CMD ["/bin/bash"]
# Fri, 27 Jul 2018 00:08:29 GMT
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-key 799058698E65316A2E7A4FF42EAE1437F7D2C623     && echo "deb http://repos.zend.com/zend-server/2018.0/deb_apache2.4 server non-free" >> /etc/apt/sources.list.d/zend-server.list     && apt-get update     && apt-get install -y       libmysqlclient20       unzip       git       curl       net-tools       zend-server-php-7.2=2018.0.0+b464     && rm -rf /var/lib/apt/lists/*     && /usr/local/zend/bin/zendctl.sh stop
# Fri, 27 Jul 2018 00:08:30 GMT
COPY file:600eecb7e31561caebcef5617a4923b3065c52e6ae17fcce39ffdcc8ca6c41db in /etc/ 
# Fri, 27 Jul 2018 00:08:30 GMT
COPY file:82de006e31874ac4e03685b3e87e988446f42138aaaf0fc5faad9cddb48040ba in /etc/apache2/conf-available 
# Fri, 27 Jul 2018 00:08:31 GMT
RUN /usr/sbin/a2enconf drop-http-proxy-header      && /usr/sbin/a2enmod headers
# Fri, 27 Jul 2018 00:08:32 GMT
ENV ZS_INIT_VERSION=0.3
# Fri, 27 Jul 2018 00:08:32 GMT
ENV ZS_INIT_SHA256=e8d441d8503808e9fc0fafc762b2cb80d4a6e68b94fede0fe41efdeac10800cb
# Fri, 27 Jul 2018 00:08:33 GMT
RUN curl -fSL -o zs-init.tar.gz "http://repos.zend.com/zs-init/zs-init-docker-${ZS_INIT_VERSION}.tar.gz"     && echo "${ZS_INIT_SHA256} *zs-init.tar.gz" | sha256sum -c -     && mkdir /usr/local/zs-init     && tar xzf zs-init.tar.gz --strip-components=1 -C /usr/local/zs-init     && rm zs-init.tar.gz
# Fri, 27 Jul 2018 00:08:33 GMT
WORKDIR /usr/local/zs-init
# Fri, 27 Jul 2018 00:09:05 GMT
RUN /usr/local/zend/bin/php /usr/local/zend/bin/composer.phar self-update && /usr/local/zend/bin/php /usr/local/zend/bin/composer.phar update
# Fri, 27 Jul 2018 00:09:23 GMT
COPY dir:15e41e43c0ea26254e53363ef64d6f20b76b254a017ddeac1bce0422b2cdaa9a in /usr/local/bin 
# Fri, 27 Jul 2018 00:09:23 GMT
COPY dir:b14dbc48195e4d5367d3aea2ed0fb26985bacb8d8229d24961363db2e2edf8f0 in /usr/local/zend/var/plugins/ 
# Fri, 27 Jul 2018 00:09:24 GMT
RUN rm /var/www/html/index.html
# Fri, 27 Jul 2018 00:09:25 GMT
COPY dir:9f1a7f23dfcf85f3c7148d98ae7914654fe8acfc4e4651f3a08427c09af24198 in /var/www/html 
# Fri, 27 Jul 2018 00:09:25 GMT
EXPOSE 80/tcp
# Fri, 27 Jul 2018 00:09:25 GMT
EXPOSE 443/tcp
# Fri, 27 Jul 2018 00:09:25 GMT
EXPOSE 10081/tcp
# Fri, 27 Jul 2018 00:09:26 GMT
EXPOSE 10082/tcp
# Fri, 27 Jul 2018 00:09:27 GMT
WORKDIR /var/www/html
# Fri, 27 Jul 2018 00:09:27 GMT
CMD ["/usr/local/bin/run"]
```

-	Layers:
	-	`sha256:8ee29e426c26c79e7ba03ccc8bbc7fe99db00ffcbccb679d9c643b5546d8dc8a`  
		Last Modified: Thu, 26 Jul 2018 22:27:22 GMT  
		Size: 43.2 MB (43228646 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e83b260b73b908ebabde46b72fc5790bf4f029b53acbbfe35da8ff8fba795ac`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e26b65fd1143ee4f9b7b6b958aeafdb996172d10b723f0bba24335a8f7ae692c`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 618.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40dca07f8222e24aab97f026444d66a7604e4ae2b708cf079ff67a90c42efa60`  
		Last Modified: Thu, 26 Jul 2018 22:26:53 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b420ae9e10b3f6a74f527914bc3c766b128435a62eca1061f41167205d5b0230`  
		Last Modified: Thu, 26 Jul 2018 22:26:54 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8497cfbaf872bab1de35f30b459e2e1fcc60d613cd22aa96d909d41a491dcea5`  
		Last Modified: Fri, 27 Jul 2018 00:14:02 GMT  
		Size: 287.6 MB (287580521 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b65b83a9fd93a2d731ea1651b8e35425536172eddee1c1026d27c47a9433fe94`  
		Last Modified: Fri, 27 Jul 2018 00:12:26 GMT  
		Size: 220.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0ffd0fada9766a416a4fae55b6ef2cdf0cfb5412cbda152058f5f3b3fa80306`  
		Last Modified: Fri, 27 Jul 2018 00:12:25 GMT  
		Size: 260.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1b836e1ecb7d842d2b909728d0888c2ddc738db7d3e84dce2c7d7657ef374e8`  
		Last Modified: Fri, 27 Jul 2018 00:12:24 GMT  
		Size: 407.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ebecda9572edfec138f28a13d780bc4a74f1c44c8cd19422877a93571333906`  
		Last Modified: Fri, 27 Jul 2018 00:12:25 GMT  
		Size: 18.8 KB (18828 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a0831dabec74976bff96de7e74f884bb1795f33bc44005b1a7d5245c59cb240`  
		Last Modified: Fri, 27 Jul 2018 00:12:28 GMT  
		Size: 16.3 MB (16345390 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47f9292def208cb82d39f359e69752de61747a2b5450b0152115cd201c831481`  
		Last Modified: Fri, 27 Jul 2018 00:12:22 GMT  
		Size: 14.2 KB (14250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:035efdb89f13e495311cd543b6772e22bbc1eefbaeb20addb84722b9a8f5f8e2`  
		Last Modified: Fri, 27 Jul 2018 00:12:22 GMT  
		Size: 2.5 KB (2532 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f56919170f07126986f47fbc5b46de840eea88e9f3c02b9d0abeef5a28ea599e`  
		Last Modified: Fri, 27 Jul 2018 00:12:23 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e1b07e36ec6d728f4a41ba00dfd97517c3d177f751a20869a758da2384ea4cb`  
		Last Modified: Fri, 27 Jul 2018 00:12:22 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
