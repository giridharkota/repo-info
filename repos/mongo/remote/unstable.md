## `mongo:unstable`

```console
$ docker pull mongo@sha256:669483b0b75f15ba2bcef51cc22edccdcd1445f613e2db607f5efc0b355318c2
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	windows version 10.0.14393.2430; amd64
	-	windows version 10.0.16299.611; amd64
	-	windows version 10.0.17134.228; amd64

### `mongo:unstable` - linux; amd64

```console
$ docker pull mongo@sha256:3185c29f812d3eecdda6c3cce31bf9653ad0b9297493a18c19931109b37b7a3d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.5 MB (136517369 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bbcb616b5f6d1fff3271aefa2a56438f5b4b94f289606f9ef86d6ce8334a5cea`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

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
# Thu, 26 Jul 2018 23:43:48 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Thu, 26 Jul 2018 23:44:02 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 26 Jul 2018 23:44:03 GMT
ENV GOSU_VERSION=1.10
# Thu, 26 Jul 2018 23:44:03 GMT
ENV JSYAML_VERSION=3.10.0
# Tue, 31 Jul 2018 16:56:36 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Tue, 31 Jul 2018 16:56:37 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 31 Jul 2018 16:58:04 GMT
ENV GPG_KEYS=E162F504A20CDF15827F718D4B7C549A058F8B6B
# Tue, 31 Jul 2018 16:58:05 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	command -v gpgconf && gpgconf --kill all || :; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 31 Jul 2018 16:58:05 GMT
ARG MONGO_PACKAGE=mongodb-org-unstable
# Tue, 31 Jul 2018 16:58:06 GMT
ARG MONGO_REPO=repo.mongodb.org
# Tue, 31 Jul 2018 16:58:06 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable MONGO_REPO=repo.mongodb.org
# Tue, 31 Jul 2018 16:58:06 GMT
ENV MONGO_MAJOR=4.1
# Thu, 16 Aug 2018 20:38:01 GMT
ENV MONGO_VERSION=4.1.2
# Thu, 16 Aug 2018 20:38:02 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Thu, 16 Aug 2018 20:38:54 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Thu, 16 Aug 2018 20:39:08 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Thu, 16 Aug 2018 20:39:08 GMT
VOLUME [/data/db /data/configdb]
# Thu, 16 Aug 2018 20:39:08 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Thu, 16 Aug 2018 20:39:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 16 Aug 2018 20:39:09 GMT
EXPOSE 27017/tcp
# Thu, 16 Aug 2018 20:39:09 GMT
CMD ["mongod"]
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
	-	`sha256:f60a3ef68cf9f1c41a99e0427cd38edc9d326138ef998f047955fed616d4dd46`  
		Last Modified: Fri, 27 Jul 2018 00:01:41 GMT  
		Size: 2.0 KB (1986 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a9eeb4f5b1b5639fdb9285e468c9479267638eea115125c0d9b6534e02539f3`  
		Last Modified: Fri, 27 Jul 2018 00:01:41 GMT  
		Size: 2.9 MB (2946835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b2f33f1e7835bbe766565e6668c725b6bd11261dd5a378b39bdce73a6f0dc91`  
		Last Modified: Tue, 31 Jul 2018 17:03:48 GMT  
		Size: 751.4 KB (751447 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbadcc13ac8fbbb025f183be4d7d16b180dcce8548ff5375121b8ae5587ee08d`  
		Last Modified: Tue, 31 Jul 2018 17:03:47 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:189287ce8b34545504f7018fe7f97d4a9a66a5bab18037d7ad3980286439ec68`  
		Last Modified: Tue, 31 Jul 2018 17:06:05 GMT  
		Size: 1.4 KB (1429 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ced607b7f1972824dd8d3d9b8ff578468fb7e3c92c5c09c2b2dc8832572eb85e`  
		Last Modified: Thu, 16 Aug 2018 20:40:07 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73851a1713addb4eda235d19069a9520771d6bd94dd64fc6b02e5d1092162c58`  
		Last Modified: Thu, 16 Aug 2018 20:40:40 GMT  
		Size: 89.6 MB (89580337 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42b7daddf8367b6bfc4a73aa59f623b206bfcd5b964976572b1c873d59fe386a`  
		Last Modified: Thu, 16 Aug 2018 20:40:07 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b34d63a19cb186d6fe56863439a1df300b7e4347e62a263b81db3cf2223f80e`  
		Last Modified: Thu, 16 Aug 2018 20:40:07 GMT  
		Size: 3.7 KB (3711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable` - linux; arm64 variant v8

```console
$ docker pull mongo@sha256:0619f5675f27a2a46e3f89b4f92a97eb7d072f311b3c020f8a66826f260398c0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **115.8 MB (115762574 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:19caadac60f59bcc69c320a9875ef63a97f3ba467f61dea48707b6ef0d7faa90`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Fri, 27 Jul 2018 12:11:25 GMT
ADD file:245f919fbf2f9e8e80f0cf22884a2095e9f3ff0685bea98f2e8c5937553d2858 in / 
# Fri, 27 Jul 2018 12:11:27 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 27 Jul 2018 12:11:29 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 27 Jul 2018 12:11:31 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 27 Jul 2018 12:11:32 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 27 Jul 2018 12:11:33 GMT
CMD ["/bin/bash"]
# Fri, 27 Jul 2018 14:59:00 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Fri, 27 Jul 2018 14:59:28 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Fri, 27 Jul 2018 14:59:29 GMT
ENV GOSU_VERSION=1.10
# Fri, 27 Jul 2018 14:59:30 GMT
ENV JSYAML_VERSION=3.10.0
# Wed, 01 Aug 2018 09:07:41 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	command -v gpgconf && gpgconf --kill all || :; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Wed, 01 Aug 2018 09:07:43 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 01 Aug 2018 09:10:06 GMT
ENV GPG_KEYS=E162F504A20CDF15827F718D4B7C549A058F8B6B
# Wed, 01 Aug 2018 09:10:08 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	command -v gpgconf && gpgconf --kill all || :; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 01 Aug 2018 09:10:09 GMT
ARG MONGO_PACKAGE=mongodb-org-unstable
# Wed, 01 Aug 2018 09:10:09 GMT
ARG MONGO_REPO=repo.mongodb.org
# Wed, 01 Aug 2018 09:10:10 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable MONGO_REPO=repo.mongodb.org
# Wed, 01 Aug 2018 09:10:11 GMT
ENV MONGO_MAJOR=4.1
# Fri, 17 Aug 2018 09:00:34 GMT
ENV MONGO_VERSION=4.1.2
# Fri, 17 Aug 2018 09:00:36 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Fri, 17 Aug 2018 09:01:36 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Fri, 17 Aug 2018 09:01:38 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Fri, 17 Aug 2018 09:01:39 GMT
VOLUME [/data/db /data/configdb]
# Fri, 17 Aug 2018 09:01:40 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Fri, 17 Aug 2018 09:01:41 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 17 Aug 2018 09:01:42 GMT
EXPOSE 27017/tcp
# Fri, 17 Aug 2018 09:01:43 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:1d84661bedcf328ca33c60337b0167cd51a34acd8ac083d03be2658e778e4a33`  
		Last Modified: Fri, 27 Jul 2018 12:15:26 GMT  
		Size: 39.4 MB (39361254 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7952229f0c51008f9d2c699538f73c19313ff6adb1c7e774ff249ad90967e1b4`  
		Last Modified: Fri, 27 Jul 2018 12:15:14 GMT  
		Size: 847.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a7c753d28831afc8b8b323117624887a02f818a6f7f76323b8573fa546e967f`  
		Last Modified: Fri, 27 Jul 2018 12:15:13 GMT  
		Size: 534.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc39f7627e7eaa49ca5d50a7007d2e4f3187c797ac91e13e6560179ca5146d4d`  
		Last Modified: Fri, 27 Jul 2018 12:15:13 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c91ed830a826b5e867059f29069b2bf3f420c65fa8b0ded96ff077238b4f5810`  
		Last Modified: Fri, 27 Jul 2018 12:15:13 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:863bd7afe72feac5827c9f038d6f70427f3270ea600ee9187248e2e48a1d6f16`  
		Last Modified: Fri, 27 Jul 2018 15:06:46 GMT  
		Size: 2.0 KB (1997 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:426d891e6237be1ad949bb38e383438542e38129a5eb2e6df5aab79b15b660ef`  
		Last Modified: Fri, 27 Jul 2018 15:06:46 GMT  
		Size: 2.5 MB (2475057 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6af082c019368494cdd48921d6d5d899e167e16aee6019294854505afa88778a`  
		Last Modified: Wed, 01 Aug 2018 09:12:22 GMT  
		Size: 717.9 KB (717949 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ae2f81b4b15ad3f3685e60dba673e32e2801726f571d9f5699a2123728101ea`  
		Last Modified: Wed, 01 Aug 2018 09:12:21 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2474770de9537d31ae93f216e74eb5351e832b5ac01b61511b99d6ea6a152ec`  
		Last Modified: Wed, 01 Aug 2018 09:14:32 GMT  
		Size: 1.4 KB (1433 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44fa0f7b33fc1eebf6906c042877a53d3835988cd61a08fc3bbb07b573d751c2`  
		Last Modified: Fri, 17 Aug 2018 09:02:17 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f44594d6481cc70fd307149e356a90822a821a2fb85dfb1abc85cffa1690aaf4`  
		Last Modified: Fri, 17 Aug 2018 09:02:43 GMT  
		Size: 73.2 MB (73198277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a36c1fc95a40adc52f1e3f6004a417bffe9498dadfeebd0e60d950e7b829d97`  
		Last Modified: Fri, 17 Aug 2018 09:02:18 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dc1ae97ade8f43f30e1d100a6d784d098ea6b3c803b42d42c5da8904145825df`  
		Last Modified: Fri, 17 Aug 2018 09:02:17 GMT  
		Size: 3.7 KB (3709 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable` - windows version 10.0.14393.2430; amd64

```console
$ docker pull mongo@sha256:0bc129c635ad2acbe17d3a80dc3392487c7aefd808d1eefa61f264c225536399
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.6 GB (5585501666 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d81e80042e4448eedcd700327c04b9a5287aaa53eaa4c49d5404f0c623668019`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Mon, 13 Aug 2018 17:52:23 GMT
RUN Install update 10.0.14393.2430
# Fri, 17 Aug 2018 09:21:39 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Fri, 17 Aug 2018 10:45:07 GMT
ENV MONGO_VERSION=4.1.2
# Fri, 17 Aug 2018 10:45:08 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2012plus-4.1.2-signed.msi
# Fri, 17 Aug 2018 10:45:09 GMT
ENV MONGO_DOWNLOAD_SHA256=4e327fa11d290fc755b92b9c8d16102f0f3984c6bee3da5630839c2a6448dd6e
# Fri, 17 Aug 2018 10:55:08 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 17 Aug 2018 10:55:09 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 17 Aug 2018 10:55:11 GMT
EXPOSE 27017/tcp
# Fri, 17 Aug 2018 10:55:12 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 13 Dec 2016 10:53:31 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:6631c2d2a60cd7ee5b334c2725b03e4d4976abb9a19c8e8dc9b806b3752745a6`  
		Last Modified: Mon, 13 Aug 2018 17:52:23 GMT  
		Size: 1.4 GB (1441905067 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:b95dd3ea2455375b05a0040130b4b3f2bd839787743ff33b9d31af75610902b1`  
		Last Modified: Fri, 17 Aug 2018 11:36:08 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10c184870c8982c660789a489268df7ddfdef51c141feb2c7c6f36fc0d5a471a`  
		Last Modified: Fri, 17 Aug 2018 11:43:40 GMT  
		Size: 1.2 KB (1205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b0969323e0bba850411205804f7ea1efc10883c864d21c3dd304b6f8e711afd`  
		Last Modified: Fri, 17 Aug 2018 11:43:39 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea8dd95435fa72fc227eefde902aa80469266b36e5fa3ab0366a79b7150ab3da`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0deca888dc735ae61621661b24b4d727edd31c6d9d3bf48197c991f48eb7571`  
		Last Modified: Fri, 17 Aug 2018 11:43:54 GMT  
		Size: 73.6 MB (73602319 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af9b4a3ff8572e6d6e870a49113224d0575268c200f1c1973a78ab026a69a65f`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:abede38d2118a1d0e7740ebf76ea9813165247bea4520cd1f351b0f6a84503ad`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a21d8911bbee32f9bf896ba3b11dab4aac531adbef2e604a8595ca61c157dfa7`  
		Last Modified: Fri, 17 Aug 2018 11:43:37 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable` - windows version 10.0.16299.611; amd64

```console
$ docker pull mongo@sha256:787260269c72e1771f41c6e456bebf2274c3c97c6c565f48effe623fdbb93446
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.7 GB (3652600615 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:426974070729c272b4aa84a5f13acac76fc024935b5e34c37f6ece752d0ec79d`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Wed, 08 Aug 2018 23:20:54 GMT
RUN Install update 10.0.16299.611
# Fri, 17 Aug 2018 09:24:21 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Fri, 17 Aug 2018 10:55:22 GMT
ENV MONGO_VERSION=4.1.2
# Fri, 17 Aug 2018 10:55:23 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2012plus-4.1.2-signed.msi
# Fri, 17 Aug 2018 10:55:23 GMT
ENV MONGO_DOWNLOAD_SHA256=4e327fa11d290fc755b92b9c8d16102f0f3984c6bee3da5630839c2a6448dd6e
# Fri, 17 Aug 2018 11:15:07 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 17 Aug 2018 11:15:09 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 17 Aug 2018 11:15:10 GMT
EXPOSE 27017/tcp
# Fri, 17 Aug 2018 11:15:11 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c4047f78756c2319eb99557ec7139906cf11af6c91aefcc0e44ac49a5481d8e4`  
		Last Modified: Mon, 13 Aug 2018 18:28:41 GMT  
		Size: 837.8 MB (837835144 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:979b51c3a12a3db81990ebd92c5d5a3325e035f84c0503e987ede3bfd73f44df`  
		Last Modified: Fri, 17 Aug 2018 11:36:35 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3182a1ddba83b13a4e6c793cb73bbb7ff7ecfa3cff0e8f1e412533987ac52780`  
		Last Modified: Fri, 17 Aug 2018 11:44:10 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ac579ed28da847c3cdb2e1bd4426e19eb327244ddd81b72ddbb5f53d8c14a58`  
		Last Modified: Fri, 17 Aug 2018 11:44:10 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6bc79fddbd56e51803a24cfc86082fe29ff3b48f12eaf9fc6800b40b96ad8c5`  
		Last Modified: Fri, 17 Aug 2018 11:44:08 GMT  
		Size: 1.2 KB (1188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f106d857ce1de02bb9d80cde41418d3c3fbdfdf5cd66b3be9c1fbe967d79cb5b`  
		Last Modified: Fri, 17 Aug 2018 11:45:11 GMT  
		Size: 540.5 MB (540456529 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f7499bf4a02de04f23a4df69111fb23090e8a721f2e0e95633b2b3501651bbb`  
		Last Modified: Fri, 17 Aug 2018 11:44:07 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:121348fa984cecb59dc226896b0166d59de1dc50240e3a5949dbcc386f8845ab`  
		Last Modified: Fri, 17 Aug 2018 11:44:07 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f3b224544238996ec8d125cbb9af10cf20ce919c8e3ca1c32556ebfcaffc9cc1`  
		Last Modified: Fri, 17 Aug 2018 11:44:07 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable` - windows version 10.0.17134.228; amd64

```console
$ docker pull mongo@sha256:806c46a140c23c7913644f9018cada7701bfb9e09f829f3fb550d1fb30e55f1f
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **2.7 GB (2729645162 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:427fa077f38fbc956a913f0fb33767111d6f152a2b22306ed928fe10fba3676a`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Thu, 12 Apr 2018 09:20:54 GMT
RUN Apply image 10.0.17134.1
# Mon, 06 Aug 2018 18:21:55 GMT
RUN Install update 10.0.17134.228
# Fri, 17 Aug 2018 10:25:17 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Fri, 17 Aug 2018 11:15:26 GMT
ENV MONGO_VERSION=4.1.2
# Fri, 17 Aug 2018 11:15:27 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2012plus-4.1.2-signed.msi
# Fri, 17 Aug 2018 11:15:28 GMT
ENV MONGO_DOWNLOAD_SHA256=4e327fa11d290fc755b92b9c8d16102f0f3984c6bee3da5630839c2a6448dd6e
# Fri, 17 Aug 2018 11:35:17 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 17 Aug 2018 11:35:19 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 17 Aug 2018 11:35:21 GMT
EXPOSE 27017/tcp
# Fri, 17 Aug 2018 11:35:22 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:d9e8b01179bfc94a5bdb1810fbd76b999aa52016001ace2d3a4c4bc7065a9601`  
		Last Modified: Mon, 07 May 2018 21:18:35 GMT  
		Size: 1.7 GB (1659688273 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:fd59519ea2c2d73a5cba6e562d012a127d08d86dfc5067535eef141406c3750b`  
		Last Modified: Mon, 13 Aug 2018 19:10:18 GMT  
		Size: 530.1 MB (530108736 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:2cb0bbe979983a9fd8ce4fd3939699c180783e70bf8f7ab0fae0c03c1e8a6a2c`  
		Last Modified: Fri, 17 Aug 2018 11:42:08 GMT  
		Size: 1.2 KB (1208 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e4503a56cd80fdf19f9cdec576c175c72dc3dd9d8aa06e9202a42b56878601a`  
		Last Modified: Fri, 17 Aug 2018 11:45:40 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f56230de2060df583369fe210a734f053cab0b3ff6423a627595b7dc015d7f04`  
		Last Modified: Fri, 17 Aug 2018 11:45:40 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aeb3537f0bf3606753faa0aecd3e5977e5f554bc74a5a5ac6574d0fa4fd5acac`  
		Last Modified: Fri, 17 Aug 2018 11:45:38 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2537ee72af8a17b091db9369de67338ab6cfc68e3c30508f596ef3a25b11dd12`  
		Last Modified: Fri, 17 Aug 2018 11:46:41 GMT  
		Size: 539.8 MB (539839768 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3baf9e5ed910adb260c0a3f40d0f1c5959b0b92aff1e037339687d7db9a6f4ae`  
		Last Modified: Fri, 17 Aug 2018 11:45:38 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079c1ee2ff07a0d52f54c62f75318d418e994c6a763eadf1876d647c89e5f8a3`  
		Last Modified: Fri, 17 Aug 2018 11:45:38 GMT  
		Size: 1.2 KB (1201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee4f8a76b89bc8422890ac8465b4f1f06758c7152d76a9eb06301e3765efc5e1`  
		Last Modified: Fri, 17 Aug 2018 11:45:38 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
