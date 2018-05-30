## `mongo:rc`

```console
$ docker pull mongo@sha256:c071184f519b0f364f529750b415fa4d10d80b57a2bbe482eee7f00e338d1b82
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `mongo:rc` - linux; amd64

```console
$ docker pull mongo@sha256:889065dffe3ff4f32a41ef12c153950866f7a26b0b19103b9c3e46673c80ae99
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **133.1 MB (133098546 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0f0a9ba8c7d9461c3e3bccce1a974af0925c93ac91ef0e99408ee862e2e2de5`
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
# Wed, 23 May 2018 21:39:54 GMT
ENV GPG_KEYS=9DA31620334BD75D9DCB49F368818C72E52529D4
# Wed, 23 May 2018 21:39:55 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 23 May 2018 21:39:55 GMT
ARG MONGO_PACKAGE=mongodb-org
# Wed, 23 May 2018 21:39:56 GMT
ARG MONGO_REPO=repo.mongodb.org
# Wed, 23 May 2018 21:39:56 GMT
ENV MONGO_PACKAGE=mongodb-org MONGO_REPO=repo.mongodb.org
# Wed, 23 May 2018 21:39:56 GMT
ENV MONGO_MAJOR=testing
# Wed, 23 May 2018 21:39:56 GMT
ENV MONGO_VERSION=4.0.0~rc0
# Wed, 23 May 2018 21:39:57 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Wed, 23 May 2018 21:40:13 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Wed, 23 May 2018 21:40:14 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Wed, 23 May 2018 21:40:14 GMT
VOLUME [/data/db /data/configdb]
# Wed, 23 May 2018 21:40:15 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Wed, 23 May 2018 21:40:15 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 23 May 2018 21:40:15 GMT
EXPOSE 27017/tcp
# Wed, 23 May 2018 21:40:15 GMT
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
	-	`sha256:9ec4bdb3c5eb956740f46633b69737c873ada0de1868afc593ae0e9224d3b60d`  
		Last Modified: Wed, 23 May 2018 21:42:07 GMT  
		Size: 1.4 KB (1431 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cd8ea998edfcb27f9e9c28e135714c9d918d0aa0aea4c931e1c951f00b2b5b69`  
		Last Modified: Wed, 23 May 2018 21:42:07 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2837a2f745c98e786b867696fcf5cf52b5b472e525e58ebee851e57a361c6e0d`  
		Last Modified: Wed, 23 May 2018 21:42:21 GMT  
		Size: 86.4 MB (86364545 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6cf1b21f7cb295b9ff850f2a5d4307859e491bde26d2d42f5242ddf73b72e8a`  
		Last Modified: Wed, 23 May 2018 21:42:07 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9f504adde8b4d8c195fe84c63fd34c3a39b56368b0322b5c665a26725cf0604`  
		Last Modified: Wed, 23 May 2018 21:42:07 GMT  
		Size: 3.7 KB (3713 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:rc` - linux; arm64 variant v8

```console
$ docker pull mongo@sha256:788bd9049eca93459222e0e0f356e15ffe3d8ad02ee8a8c118294e1bdce81862
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **153.2 MB (153203708 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:63a84be5d65968ab10235900084fd435fecc90fc4bd177ab45cfbdf150b190dd`
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
# Fri, 25 May 2018 08:42:51 GMT
ENV GPG_KEYS=9DA31620334BD75D9DCB49F368818C72E52529D4
# Fri, 25 May 2018 08:42:53 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Fri, 25 May 2018 08:42:54 GMT
ARG MONGO_PACKAGE=mongodb-org
# Fri, 25 May 2018 08:42:54 GMT
ARG MONGO_REPO=repo.mongodb.org
# Fri, 25 May 2018 08:42:56 GMT
ENV MONGO_PACKAGE=mongodb-org MONGO_REPO=repo.mongodb.org
# Fri, 25 May 2018 08:42:57 GMT
ENV MONGO_MAJOR=testing
# Fri, 25 May 2018 08:42:58 GMT
ENV MONGO_VERSION=4.0.0~rc0
# Fri, 25 May 2018 08:43:00 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Fri, 25 May 2018 08:44:17 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Fri, 25 May 2018 08:44:20 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Fri, 25 May 2018 08:44:21 GMT
VOLUME [/data/db /data/configdb]
# Fri, 25 May 2018 08:44:23 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Fri, 25 May 2018 08:44:25 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 25 May 2018 08:44:26 GMT
EXPOSE 27017/tcp
# Fri, 25 May 2018 08:44:27 GMT
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
	-	`sha256:46f1763e2454a49b74370492e8227f5f2e03602515ffdd73a1527182c47f3a74`  
		Last Modified: Fri, 25 May 2018 08:47:01 GMT  
		Size: 1.4 KB (1429 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b0693304e27ca5ebf608e88e4aa07825265894d4ff15d328787b4313296f71d`  
		Last Modified: Fri, 25 May 2018 08:47:01 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66c26cb6ff019522ea8829a40d4d1e897b5ebb897fb798fd4cc073b480b98fb6`  
		Last Modified: Fri, 25 May 2018 08:48:15 GMT  
		Size: 110.8 MB (110776876 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d44f56a7c163ce792aa841d56e41c6c50eb6239e42acc1cc846e5aa930929497`  
		Last Modified: Fri, 25 May 2018 08:47:01 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70c6c9c99bb5f883ee6e0fb1a4ab72e401712e3650630153ee0d2ecd6c0d72b7`  
		Last Modified: Fri, 25 May 2018 08:47:01 GMT  
		Size: 3.7 KB (3708 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip