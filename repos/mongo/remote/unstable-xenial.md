## `mongo:unstable-xenial`

```console
$ docker pull mongo@sha256:2ccfa851a4d2c22167d1fe18f06c16fc786f4ddd86cdd2ef674ba29af0d38ee9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `mongo:unstable-xenial` - linux; amd64

```console
$ docker pull mongo@sha256:343dd0417a21dce4e5450a5fa072d02ba371506a3c1ea4fb873b267fa56f0e23
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **131.6 MB (131598953 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e3b7991cef630f68e737e55628fcaaf7cf3263f371e111bc3b319ee70588e185`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Fri, 27 Apr 2018 23:30:17 GMT
ADD file:592c2540de1c707636622213ee30ff5b6f8be0a48bb25c97edc7204ea4df1a81 in / 
# Fri, 27 Apr 2018 23:30:18 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 27 Apr 2018 23:30:19 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 27 Apr 2018 23:30:19 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 27 Apr 2018 23:30:20 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 27 Apr 2018 23:30:21 GMT
CMD ["/bin/bash"]
# Wed, 23 May 2018 21:38:28 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Wed, 23 May 2018 21:38:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Wed, 23 May 2018 21:38:53 GMT
ENV GOSU_VERSION=1.10
# Wed, 23 May 2018 21:38:53 GMT
ENV JSYAML_VERSION=3.10.0
# Wed, 23 May 2018 21:39:04 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Wed, 23 May 2018 21:39:05 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 23 May 2018 21:39:05 GMT
ENV GPG_KEYS=BD8C80D9C729D00524E068E03DAB71713396F72B
# Wed, 23 May 2018 21:39:06 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 23 May 2018 21:39:06 GMT
ARG MONGO_PACKAGE=mongodb-org-unstable
# Wed, 23 May 2018 21:39:07 GMT
ARG MONGO_REPO=repo.mongodb.org
# Wed, 23 May 2018 21:39:07 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable MONGO_REPO=repo.mongodb.org
# Wed, 23 May 2018 21:39:07 GMT
ENV MONGO_MAJOR=3.7
# Wed, 23 May 2018 21:39:07 GMT
ENV MONGO_VERSION=3.7.9
# Wed, 23 May 2018 21:39:08 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Wed, 23 May 2018 21:39:39 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Wed, 23 May 2018 21:39:40 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Wed, 23 May 2018 21:39:40 GMT
VOLUME [/data/db /data/configdb]
# Wed, 23 May 2018 21:39:41 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Wed, 23 May 2018 21:39:41 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 23 May 2018 21:39:41 GMT
EXPOSE 27017/tcp
# Wed, 23 May 2018 21:39:41 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:297061f60c367c17cfd016c97a8cb24f5308db2c913def0f85d7a6848c0a17fa`  
		Last Modified: Fri, 20 Apr 2018 22:11:58 GMT  
		Size: 43.0 MB (43026850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9ccef17b516e916aa8abe7817876211000c27150b908bdffcdeeba938cd004c`  
		Last Modified: Fri, 27 Apr 2018 23:35:41 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbc33716854d9e2ef2de9769422f498f5320ffa41cb79336e7a88fbb6c3ef844`  
		Last Modified: Fri, 27 Apr 2018 23:35:41 GMT  
		Size: 621.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fe36b178d25214195af42254bc7d5d64a269f654ef8801bbeb0b6a70a618353`  
		Last Modified: Fri, 27 Apr 2018 23:35:41 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:686596545a94a0f0bf822e442cfd28fbd8a769f28e5f4018d7c24576dc6c3aac`  
		Last Modified: Fri, 27 Apr 2018 23:35:41 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72c79e8ae4264589c0bd01e61cdc7a98d79a965983d19960c41ad7559424e902`  
		Last Modified: Wed, 23 May 2018 21:41:25 GMT  
		Size: 2.0 KB (1995 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28966b29e6bb03f03a0beb03c8f808866986695831e6594a57ce85d701cf6706`  
		Last Modified: Wed, 23 May 2018 21:41:25 GMT  
		Size: 2.9 MB (2946008 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e37ba80ef380a32efbe4f5e6d630debb06a2a67bcba8910f738f9a70c78e7312`  
		Last Modified: Wed, 23 May 2018 21:41:24 GMT  
		Size: 751.0 KB (751018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5ba65be854f4f96eaadb3d98070e5875b57bcdbe43ead8b3d1669a1abe8e2e7`  
		Last Modified: Wed, 23 May 2018 21:41:24 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1606d294745a136975aaeb9571323f73216524f0f52f8e8e5045f487e2aff39`  
		Last Modified: Wed, 23 May 2018 21:41:22 GMT  
		Size: 1.4 KB (1434 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d8c6300fec5f11d7ebdf0678687d8b152d8dd90d7d0aad083f52d8a99e66bbc`  
		Last Modified: Wed, 23 May 2018 21:41:22 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:514dfb45722ae025df11830a0d3b0adf6969c2b673a77f45c4b0fd29b7666e75`  
		Last Modified: Wed, 23 May 2018 21:41:39 GMT  
		Size: 84.9 MB (84864950 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3063fcb00560af742a2445fa2ba3fa8c5dd60f8ee346e4e16b6a777369c117db`  
		Last Modified: Wed, 23 May 2018 21:41:22 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfb52bcc13439ddd5c1b5973aeeba8b1daea5fe611c35570917eda75ba0e910a`  
		Last Modified: Wed, 23 May 2018 21:41:23 GMT  
		Size: 3.7 KB (3714 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:unstable-xenial` - linux; arm64 variant v8

```console
$ docker pull mongo@sha256:ef3d6887d2892566babea7d2617e6a105377f30bd7ff971d5e235ecaa9024184
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **151.8 MB (151829675 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:afbdd93dbb7dbf56640097d84dcfaeae205fa38e98b958df6cce6c0d75b0165a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Tue, 01 May 2018 01:12:52 GMT
ADD file:fef3655a03a1c7f1533148016797b982955b3d5556f32c777214b8426028509b in / 
# Tue, 01 May 2018 01:12:56 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 01 May 2018 01:13:04 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 01:13:10 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 01 May 2018 01:13:15 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 01 May 2018 01:13:20 GMT
CMD ["/bin/bash"]
# Fri, 25 May 2018 08:40:04 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Fri, 25 May 2018 08:40:28 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 08:40:29 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 08:40:30 GMT
ENV JSYAML_VERSION=3.10.0
# Fri, 25 May 2018 08:40:50 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Fri, 25 May 2018 08:40:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Fri, 25 May 2018 08:40:53 GMT
ENV GPG_KEYS=BD8C80D9C729D00524E068E03DAB71713396F72B
# Fri, 25 May 2018 08:40:55 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Fri, 25 May 2018 08:40:55 GMT
ARG MONGO_PACKAGE=mongodb-org-unstable
# Fri, 25 May 2018 08:40:56 GMT
ARG MONGO_REPO=repo.mongodb.org
# Fri, 25 May 2018 08:40:56 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable MONGO_REPO=repo.mongodb.org
# Fri, 25 May 2018 08:40:57 GMT
ENV MONGO_MAJOR=3.7
# Fri, 25 May 2018 08:40:58 GMT
ENV MONGO_VERSION=3.7.9
# Fri, 25 May 2018 08:40:59 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Fri, 25 May 2018 08:42:07 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Fri, 25 May 2018 08:42:16 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Fri, 25 May 2018 08:42:17 GMT
VOLUME [/data/db /data/configdb]
# Fri, 25 May 2018 08:42:19 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Fri, 25 May 2018 08:42:19 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 25 May 2018 08:42:20 GMT
EXPOSE 27017/tcp
# Fri, 25 May 2018 08:42:21 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:83c016a9a148a71d05469a3994d54eb7eb9c3d40a65e07bf68788018a71d951b`  
		Last Modified: Mon, 23 Apr 2018 14:56:07 GMT  
		Size: 39.2 MB (39223827 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8a1976297de94ed1f5c4c0f13b0b25199c6d6ca003ddfc3e873938aa2f8e86b`  
		Last Modified: Tue, 01 May 2018 01:17:18 GMT  
		Size: 856.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:167d83417bbef32ed4713f4224bcb9f9573597ee6d91174dc7403ce457f145d2`  
		Last Modified: Tue, 01 May 2018 01:17:18 GMT  
		Size: 614.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2544c5c45beca34c948aca9c981d56b587a973354727e4c97dc99d88227fb6a`  
		Last Modified: Tue, 01 May 2018 01:17:18 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb92ef1d410a96b276ec1425b000d80d5c1d914688aae8bce3e6f20d8a5a7a5f`  
		Last Modified: Tue, 01 May 2018 01:17:19 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55133372d30b5944da324c510c56a654de356b4e50a127fcffb7beb74c1e0da7`  
		Last Modified: Fri, 25 May 2018 08:45:02 GMT  
		Size: 2.0 KB (1991 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70081c1c602ffca6670e61e1b7452b02b1e74bed8f4e68074f4ac921de5d6f0e`  
		Last Modified: Fri, 25 May 2018 08:45:03 GMT  
		Size: 2.5 MB (2475007 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4003ba073adbd4c4c25a0dbcff1d4094a220a088a69810b784ea59e8932a59ec`  
		Last Modified: Fri, 25 May 2018 08:45:01 GMT  
		Size: 717.9 KB (717880 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b08920d2e7cf333d5a15d9325cd13ff6864e8863c26ae0327244cf9bea134875`  
		Last Modified: Fri, 25 May 2018 08:45:00 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0806db873e5ef926a633bf7a002438d62483db4fe042ab13ecc0fefd9b8a8549`  
		Last Modified: Fri, 25 May 2018 08:44:58 GMT  
		Size: 1.4 KB (1434 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f21708b986047de70d3fbaefd764cc432b35dcd2922aeeef9ad80e6739e8371`  
		Last Modified: Fri, 25 May 2018 08:44:58 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b05d35e137e861e45e8982b93ba5deaacf0984bb2652809eec8e4bd1afc67a1`  
		Last Modified: Fri, 25 May 2018 08:46:16 GMT  
		Size: 109.4 MB (109402835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d756010910ce09eed246c680a96ba5ad52b6ef4725b9b9e96b34acfa2050e9a8`  
		Last Modified: Fri, 25 May 2018 08:44:58 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:120904c0111ef92825d312f3114d97e39391ecf654ad0ac9460c5adb3e6aea35`  
		Last Modified: Fri, 25 May 2018 08:44:58 GMT  
		Size: 3.7 KB (3711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip