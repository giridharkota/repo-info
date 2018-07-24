## `mongo:unstable-xenial`

```console
$ docker pull mongo@sha256:9b66c9b94a1b83030a702bb6bca3b748559774b87ad7273eb9d2c79ee85e6557
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `mongo:unstable-xenial` - linux; amd64

```console
$ docker pull mongo@sha256:9cfe7ed0cf462441b3f0e70cf5de2e244b18929f0ffb2d220032e6a8b2d92638
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **133.3 MB (133255573 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:88daaf15608f7ffb5c8fc948d4d94457ab34f66aaa462e7986b233317201bb90`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Tue, 17 Jul 2018 00:53:59 GMT
ADD file:7b8419bb9079c6d91ceeb2d0f35c46bcb8083d9d666eb21fda765ed755a07840 in / 
# Tue, 17 Jul 2018 00:54:00 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 17 Jul 2018 00:54:01 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 00:54:02 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 17 Jul 2018 00:54:02 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 17 Jul 2018 00:54:02 GMT
CMD ["/bin/bash"]
# Tue, 17 Jul 2018 04:13:37 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Tue, 17 Jul 2018 04:13:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 04:13:54 GMT
ENV GOSU_VERSION=1.10
# Tue, 17 Jul 2018 04:13:54 GMT
ENV JSYAML_VERSION=3.10.0
# Tue, 17 Jul 2018 04:14:04 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Tue, 17 Jul 2018 04:14:05 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Sat, 21 Jul 2018 07:31:46 GMT
ENV GPG_KEYS=E162F504A20CDF15827F718D4B7C549A058F8B6B
# Sat, 21 Jul 2018 07:31:47 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Sat, 21 Jul 2018 07:31:47 GMT
ARG MONGO_PACKAGE=mongodb-org-unstable
# Sat, 21 Jul 2018 07:31:48 GMT
ARG MONGO_REPO=repo.mongodb.org
# Sat, 21 Jul 2018 07:31:48 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable MONGO_REPO=repo.mongodb.org
# Sat, 21 Jul 2018 07:31:48 GMT
ENV MONGO_MAJOR=4.1
# Sat, 21 Jul 2018 07:31:49 GMT
ENV MONGO_VERSION=4.1.1
# Sat, 21 Jul 2018 07:31:50 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Sat, 21 Jul 2018 07:32:41 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Sat, 21 Jul 2018 07:32:42 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Sat, 21 Jul 2018 07:32:42 GMT
VOLUME [/data/db /data/configdb]
# Sat, 21 Jul 2018 07:32:43 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Sat, 21 Jul 2018 07:32:43 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 21 Jul 2018 07:32:43 GMT
EXPOSE 27017/tcp
# Sat, 21 Jul 2018 07:32:44 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:3620e2d282dce98978bc2ae770aa43121cfa88cafdb8888d552bfd96ade2c857`  
		Last Modified: Mon, 09 Jul 2018 15:05:32 GMT  
		Size: 43.2 MB (43190074 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef22f5e4b3b2cfcefabf6ae23afc6eec160c1a9ab32ba72f9117feee454a6dc5`  
		Last Modified: Tue, 17 Jul 2018 00:59:21 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99f229f854da0ebac56b80462718952353fe22745701123dee20cbd24dede33d`  
		Last Modified: Tue, 17 Jul 2018 00:59:21 GMT  
		Size: 618.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4fe433abe16a89c38c06a4e91d1db85448407c4783d6cfbde3a03c4d71481d24`  
		Last Modified: Tue, 17 Jul 2018 00:59:22 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9b72a16d85e58632c1b2114dd92916b5c923f697a667ae56fd14a9a9a33869b`  
		Last Modified: Tue, 17 Jul 2018 00:59:21 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1757e0920c931d89a7bd21c6c8c1a2fdf46dde51618efca1ebc28980179cf08`  
		Last Modified: Tue, 17 Jul 2018 04:19:04 GMT  
		Size: 2.0 KB (1988 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ad61d16333c1e67cf913d1e225e170895ee9551a930fef8a568c97b09a71ed0`  
		Last Modified: Tue, 17 Jul 2018 04:19:03 GMT  
		Size: 2.9 MB (2946412 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b55b55716bc598f4d649c91b0c3d5488230836771fe87e12955be7236151cf9`  
		Last Modified: Tue, 17 Jul 2018 04:19:02 GMT  
		Size: 751.0 KB (750984 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9e1a31a5de88e167f03c1e3d692cae35cae0ebb41ecca648a0e0b628983e5bb`  
		Last Modified: Tue, 17 Jul 2018 04:19:01 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2428c737e4113d76d4790edd9f12b3ca0a034e89b214c8879e02710d1a459c1f`  
		Last Modified: Sat, 21 Jul 2018 07:33:16 GMT  
		Size: 1.4 KB (1431 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:133f8f4465e62602dd82e286ca0126d55409834f7cbee2275844c7fa3679bcf8`  
		Last Modified: Sat, 21 Jul 2018 07:33:17 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c78fe9beb5aa2954705d93c508e5d59b75366c2bcc4751b7217f5deb03f189b3`  
		Last Modified: Sat, 21 Jul 2018 07:33:50 GMT  
		Size: 86.4 MB (86357995 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d72518557ba5918c445fdfd4b12ae481d4e8c8ccdf72fd94fce3608687d17929`  
		Last Modified: Sat, 21 Jul 2018 07:33:16 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6b2e58bcd92da31870c76b5175512d957776e08be6834368c9c701841e02f90`  
		Last Modified: Sat, 21 Jul 2018 07:33:17 GMT  
		Size: 3.7 KB (3709 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable-xenial` - linux; arm64 variant v8

```console
$ docker pull mongo@sha256:dfcd78e1407e3f1512aad9eb84ae2e28e30a107c337c19aabca2ec85693222a2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **153.3 MB (153250984 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:200d14f20fc873c64788692191bc5e94a0d3b2545e4dca79c0222c15db13b14d`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Wed, 06 Jun 2018 09:38:27 GMT
ADD file:4d66a098626c376a1c073e0332a6c8d18aa8cc0dbadb329fd506fdfa59793143 in / 
# Wed, 06 Jun 2018 09:38:30 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 06 Jun 2018 09:38:32 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 09:38:34 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 06 Jun 2018 09:38:37 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 06 Jun 2018 09:38:37 GMT
CMD ["/bin/bash"]
# Wed, 06 Jun 2018 10:41:32 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Wed, 06 Jun 2018 10:42:08 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 10:42:10 GMT
ENV GOSU_VERSION=1.10
# Wed, 06 Jun 2018 10:42:12 GMT
ENV JSYAML_VERSION=3.10.0
# Wed, 06 Jun 2018 10:42:44 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Wed, 06 Jun 2018 10:42:54 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Sat, 21 Jul 2018 09:13:50 GMT
ENV GPG_KEYS=E162F504A20CDF15827F718D4B7C549A058F8B6B
# Sat, 21 Jul 2018 09:13:53 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Sat, 21 Jul 2018 09:13:54 GMT
ARG MONGO_PACKAGE=mongodb-org-unstable
# Sat, 21 Jul 2018 09:13:55 GMT
ARG MONGO_REPO=repo.mongodb.org
# Sat, 21 Jul 2018 09:13:55 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable MONGO_REPO=repo.mongodb.org
# Sat, 21 Jul 2018 09:13:56 GMT
ENV MONGO_MAJOR=4.1
# Sat, 21 Jul 2018 09:13:57 GMT
ENV MONGO_VERSION=4.1.1
# Sat, 21 Jul 2018 09:13:58 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Sat, 21 Jul 2018 09:15:01 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Sat, 21 Jul 2018 09:15:02 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Sat, 21 Jul 2018 09:15:03 GMT
VOLUME [/data/db /data/configdb]
# Sat, 21 Jul 2018 09:15:04 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Sat, 21 Jul 2018 09:15:05 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 21 Jul 2018 09:15:06 GMT
EXPOSE 27017/tcp
# Sat, 21 Jul 2018 09:15:06 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:21707c5c72669fddc5511cbdced3327d864e1cb7aa4d1d273beb008be29c82dc`  
		Last Modified: Mon, 28 May 2018 14:58:41 GMT  
		Size: 39.3 MB (39283293 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2b2716544889f4e40c0d32347e352b47046e2b8f272a78cd166f50462a2010a`  
		Last Modified: Wed, 06 Jun 2018 09:43:13 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3396a4a881d875be937f4b13c557a03aca52cb7d058d39395da1f896f8feda23`  
		Last Modified: Wed, 06 Jun 2018 09:43:12 GMT  
		Size: 612.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f138533abd45add28f8a1ca64239b68a83458387b0d2b1066002ca9b94f6215`  
		Last Modified: Wed, 06 Jun 2018 09:43:12 GMT  
		Size: 856.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7992862215acd8daf7477cdc3dea5fbf67934989b013a18828f88e64ea00d70a`  
		Last Modified: Wed, 06 Jun 2018 09:43:12 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae65166e186b0f755bceb763832e7e1c061687a5b6d2fa3dae1f1fce6e19f1e3`  
		Last Modified: Wed, 06 Jun 2018 10:48:14 GMT  
		Size: 2.0 KB (1992 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a03fc6d46aeeb4deb87079ac87fc8579d68283ff85a7a3bc12349c2175230490`  
		Last Modified: Wed, 06 Jun 2018 10:48:17 GMT  
		Size: 2.5 MB (2474969 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccc1a4d2360f90254ba7da51561477e79e2bb549c3ede15f70b2361117d0e24f`  
		Last Modified: Wed, 06 Jun 2018 10:48:14 GMT  
		Size: 717.9 KB (717900 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89c801b5777b67a93934e6ac32be46391aa742ad3b0365b6b8d3220a23884df4`  
		Last Modified: Wed, 06 Jun 2018 10:48:12 GMT  
		Size: 113.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:935777ad0d3e31fb2ab952e9f5c363c500ead2e424f22f49e857a0fa7cd8215b`  
		Last Modified: Sat, 21 Jul 2018 09:15:42 GMT  
		Size: 1.4 KB (1435 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5bd6682ce21d57534311eb334879ef21ae4c7aad2a38c39126cd740be7351245`  
		Last Modified: Sat, 21 Jul 2018 09:15:42 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:028aeb3a67f2f388d9c01023ab684c5ba03d8afdc641a92b7fad5e9007c46578`  
		Last Modified: Sat, 21 Jul 2018 09:16:25 GMT  
		Size: 110.8 MB (110764702 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bce95fda75f626408cae1374da11db1f105d088e0530cb358630f9abe7f54a2`  
		Last Modified: Sat, 21 Jul 2018 09:15:42 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a9d5ba8fc9b68bdb3886d9d77b3e510b8d5fae31f214f0e7eadd7fdc5e510cc`  
		Last Modified: Sat, 21 Jul 2018 09:15:41 GMT  
		Size: 3.7 KB (3711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip