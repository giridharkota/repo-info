## `flink:scala_2.11`

```console
$ docker pull flink@sha256:44650d479a04a92604a2d38ab24fc2692aee33390798e7b014cf58168764b2c3
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `flink:scala_2.11` - linux; amd64

```console
$ docker pull flink@sha256:27550e561bff66d7b330057bda210f3b689a8aedf56aefb4adbc72c6a1c488ea
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **450.4 MB (450417265 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:aa7c3b80f354c70203186fcd8a06c4f8015f635465353e0ed4c795e355cc25af`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Tue, 17 Jul 2018 00:27:24 GMT
ADD file:370028dca6e8ca9ed228549d52231cf8139515cc3a14c00aaed75a60b679775f in / 
# Tue, 17 Jul 2018 00:27:24 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 03:12:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 03:13:02 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 06:19:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:19:33 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:19:34 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:19:34 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:19:35 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 14 Aug 2018 20:34:46 GMT
ENV JAVA_VERSION=8u181
# Tue, 14 Aug 2018 20:34:46 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Tue, 14 Aug 2018 20:34:46 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 14 Aug 2018 20:35:31 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 14 Aug 2018 20:35:34 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 14 Aug 2018 21:30:09 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Tue, 14 Aug 2018 21:30:09 GMT
ENV GOSU_VERSION=1.7
# Tue, 14 Aug 2018 21:30:16 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Tue, 14 Aug 2018 21:43:43 GMT
ENV FLINK_VERSION=1.6.0 HADOOP_SCALA_VARIANT=scala_2.11
# Tue, 14 Aug 2018 21:43:43 GMT
ENV FLINK_HOME=/opt/flink
# Tue, 14 Aug 2018 21:43:43 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 21:43:44 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Tue, 14 Aug 2018 21:43:45 GMT
WORKDIR /opt/flink
# Tue, 14 Aug 2018 21:43:45 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz
# Tue, 14 Aug 2018 21:43:45 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz.asc
# Tue, 14 Aug 2018 21:43:46 GMT
COPY file:d9b980b40ddcfab2700a72e4088616452368e14c4f8fbee56f3258ac7f5dd913 in /KEYS 
# Tue, 14 Aug 2018 21:44:27 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Tue, 14 Aug 2018 21:44:32 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Tue, 14 Aug 2018 21:44:33 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 14 Aug 2018 21:44:33 GMT
EXPOSE 6123/tcp 8081/tcp
# Tue, 14 Aug 2018 21:44:33 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:55cbf04beb7001d222c71bfdeae780bda19d5cb37b8dbd65ff0d3e6a0b9b74e6`  
		Last Modified: Tue, 17 Jul 2018 00:42:31 GMT  
		Size: 45.3 MB (45310044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1607093a898cc241de8712e4361dcd907898fff35b945adca42db3963f3827b3`  
		Last Modified: Tue, 17 Jul 2018 03:53:34 GMT  
		Size: 10.7 MB (10740168 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a8ea045c9261c180a34df19cfc9bb3c3f28f29b279bf964ee801536e8244f2f`  
		Last Modified: Tue, 17 Jul 2018 03:53:32 GMT  
		Size: 4.3 MB (4336107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1290813abd9d0a07ce709b4e491f4194f2b854295d93bdc068b7a576756fb515`  
		Last Modified: Tue, 17 Jul 2018 07:03:58 GMT  
		Size: 852.9 KB (852875 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6b982ad6d7f57b4a8a4052561dc7b0377bd8d4028bce8a93a4d31e60b79329`  
		Last Modified: Tue, 17 Jul 2018 07:03:58 GMT  
		Size: 246.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:abb029e68402beca7edc4627d5034aa72b37c74d8af9badb3284a69f17b91bb6`  
		Last Modified: Tue, 17 Jul 2018 07:03:57 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d068d0a738e5053cbca5643bc07bc278f76d3769cd69b8afda717c695c210f18`  
		Last Modified: Tue, 14 Aug 2018 20:46:59 GMT  
		Size: 122.1 MB (122120099 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42ee47bb0c52e5210fb8b964b20a471bc9591949cc7c6c45d14d4679eae2f2ed`  
		Last Modified: Tue, 14 Aug 2018 20:46:23 GMT  
		Size: 246.7 KB (246699 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4a089aadceca0332c265738b178586bd1a2ad8c3e5ce9bbf77937113924e48d`  
		Last Modified: Tue, 14 Aug 2018 21:45:30 GMT  
		Size: 466.4 KB (466399 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:56b0387aea6264321be1ae882a9e028fe975ec01540943813da0ccb82ceb0800`  
		Last Modified: Tue, 14 Aug 2018 21:45:30 GMT  
		Size: 819.2 KB (819185 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:835e0d4fcb1fa980cd30dc2c28f6632aae54bc3a2366640b985e97a37b545988`  
		Last Modified: Tue, 14 Aug 2018 22:08:48 GMT  
		Size: 4.6 KB (4613 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1fae07ecc594f83a4109d8a4f4b15932c387f56a63ea841bb00075a924a458f`  
		Last Modified: Tue, 14 Aug 2018 22:08:49 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f56bae56e3f8959e7223340dbe90def155fc81ba661f1747d1868574c477a80`  
		Last Modified: Tue, 14 Aug 2018 22:08:48 GMT  
		Size: 59.3 KB (59338 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:062b50e0135073b32421824c1de111caad3f1cc79cc71291603a09a9d64d50c5`  
		Last Modified: Tue, 14 Aug 2018 22:09:17 GMT  
		Size: 265.5 MB (265460130 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87034de9cb3952fce6ded8d1e17f187f1e85414cc3c2ec968dd75671339550ab`  
		Last Modified: Tue, 14 Aug 2018 22:08:48 GMT  
		Size: 1.1 KB (1117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `flink:scala_2.11` - linux; arm variant v5

```console
$ docker pull flink@sha256:f495990d62db7db571948c4f358d994623f87a54083806bc3e52b0d3a6ebbe66
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **437.8 MB (437762404 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1ac16ca25efe7d89fa89afcbb3f094507c3f30ae53bb7426b42a010668d6f639`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Tue, 17 Jul 2018 08:55:48 GMT
ADD file:bf9eafe81eb19079a2f2055b6727392afa823dfa125a4b1696537cf603115e52 in / 
# Tue, 17 Jul 2018 08:55:49 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:49:03 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 11:49:19 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 12:43:03 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:43:03 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 12:43:04 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 12:43:05 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:43:06 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 08:51:38 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 08:51:38 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 08:51:38 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 08:52:41 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 08:52:46 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 09:26:02 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 09:26:02 GMT
ENV GOSU_VERSION=1.7
# Wed, 15 Aug 2018 09:26:06 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Wed, 15 Aug 2018 09:36:29 GMT
ENV FLINK_VERSION=1.6.0 HADOOP_SCALA_VARIANT=scala_2.11
# Wed, 15 Aug 2018 09:36:29 GMT
ENV FLINK_HOME=/opt/flink
# Wed, 15 Aug 2018 09:36:29 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 15 Aug 2018 09:36:30 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Wed, 15 Aug 2018 09:36:31 GMT
WORKDIR /opt/flink
# Wed, 15 Aug 2018 09:36:31 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz
# Wed, 15 Aug 2018 09:36:31 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz.asc
# Wed, 15 Aug 2018 09:36:32 GMT
COPY file:d9b980b40ddcfab2700a72e4088616452368e14c4f8fbee56f3258ac7f5dd913 in /KEYS 
# Wed, 15 Aug 2018 09:39:01 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Wed, 15 Aug 2018 09:39:01 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Wed, 15 Aug 2018 09:39:01 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 15 Aug 2018 09:39:02 GMT
EXPOSE 6123/tcp 8081/tcp
# Wed, 15 Aug 2018 09:39:02 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:e0468d51364430736eb1d0d85f3dd880c4bebe4015787330b6c9227843acb4a6`  
		Last Modified: Tue, 17 Jul 2018 09:08:05 GMT  
		Size: 44.0 MB (44033063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ad0b2352b28fea9acd0f76fa8814e168b15f21efe51602d644728d229d9bab9`  
		Last Modified: Tue, 17 Jul 2018 12:02:04 GMT  
		Size: 9.8 MB (9810102 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:864851e50dc1192bbdfa9be12666036d86148172f3ead845ee38c8033885580e`  
		Last Modified: Tue, 17 Jul 2018 12:02:03 GMT  
		Size: 4.2 MB (4153726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5835e5acfad7d56ae63ec170f3775123ea187c36c77147a58b1c8f77e944c094`  
		Last Modified: Tue, 17 Jul 2018 12:56:10 GMT  
		Size: 845.9 KB (845860 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48ef3838b860ad2926373a0286edee0ed0209f0c88b9a118784b44620950df6b`  
		Last Modified: Tue, 17 Jul 2018 12:56:10 GMT  
		Size: 246.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0d09f94a09042fc2888b335d412166395678b9f17e6d701e4fed6ef5dc4e8a4`  
		Last Modified: Tue, 17 Jul 2018 12:56:10 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f06c007e7d31db7059d887a323bff2e339a80a5ea263f021b7b84482ab2b7153`  
		Last Modified: Wed, 15 Aug 2018 08:57:14 GMT  
		Size: 111.9 MB (111903307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f4667c9b2ab3c079f7692236368b8eb8b9a83fbffa768b51ab8dc37759acb5b`  
		Last Modified: Wed, 15 Aug 2018 08:56:45 GMT  
		Size: 246.7 KB (246731 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:126601e54b0be03ef610d0c4e243cfedcb88dde922e0662d1104e1c143e85403`  
		Last Modified: Wed, 15 Aug 2018 09:39:29 GMT  
		Size: 466.2 KB (466210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:958b55aa1c69c9ae63011e2ac6592db2f813a2106f8542b91526b02d633bb68f`  
		Last Modified: Wed, 15 Aug 2018 09:39:28 GMT  
		Size: 777.7 KB (777669 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c4fb4e128d2a28827ab6ff903339ccfefe502016e4a55cb01ab980bed8340a2`  
		Last Modified: Wed, 15 Aug 2018 09:48:31 GMT  
		Size: 4.5 KB (4531 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10f5bf3b89cd39125852ac95044ec547e77156e7bfe2a08b90653e9feb4daa2e`  
		Last Modified: Wed, 15 Aug 2018 09:48:31 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2dab2447e0400b005c29df615e1812a820958a2285bd515c2cf279e4ffb8c1a`  
		Last Modified: Wed, 15 Aug 2018 09:48:31 GMT  
		Size: 59.3 KB (59336 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:966f1ba31cdfd8ff5f7af0116d8ce9fa4339beea7b9c9c6f1da3c5657f828a74`  
		Last Modified: Wed, 15 Aug 2018 09:49:03 GMT  
		Size: 265.5 MB (265460227 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48ad52c7d9e895508737eeea8ca642ff5d59c2cc90b1f9d5c574d2bd08305b43`  
		Last Modified: Wed, 15 Aug 2018 09:48:31 GMT  
		Size: 1.1 KB (1118 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `flink:scala_2.11` - linux; arm variant v7

```console
$ docker pull flink@sha256:b744902361be279d20e40215adc5b92fdb7bad798932bc6917508d790a16b7dd
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **462.8 MB (462820519 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c4af5b46ec8834c79fd023d33032a74440e122f8bf079b40ad2f5d8c84ba62ab`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Sat, 28 Apr 2018 12:04:18 GMT
ADD file:c7fba27b02c4bda63faef7eb30156a55feb4c0e9ecd529a24dd8d62942c2f83c in / 
# Sat, 28 Apr 2018 12:04:19 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:13:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:13:58 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:59:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:59:16 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:59:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:59:18 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:59:18 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 05 May 2018 12:59:19 GMT
ENV JAVA_VERSION=8u171
# Sat, 05 May 2018 12:59:27 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Sat, 05 May 2018 12:59:27 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Sat, 05 May 2018 13:00:26 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 05 May 2018 13:00:28 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Fri, 20 Jul 2018 11:57:58 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Fri, 20 Jul 2018 11:58:00 GMT
ENV GOSU_VERSION=1.7
# Fri, 20 Jul 2018 11:58:04 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Tue, 14 Aug 2018 12:02:37 GMT
ENV FLINK_VERSION=1.6.0 HADOOP_SCALA_VARIANT=scala_2.11
# Tue, 14 Aug 2018 12:02:37 GMT
ENV FLINK_HOME=/opt/flink
# Tue, 14 Aug 2018 12:02:37 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 14 Aug 2018 12:02:38 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Tue, 14 Aug 2018 12:02:38 GMT
WORKDIR /opt/flink
# Tue, 14 Aug 2018 12:02:39 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz
# Tue, 14 Aug 2018 12:02:39 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz.asc
# Tue, 14 Aug 2018 12:02:39 GMT
COPY file:d9b980b40ddcfab2700a72e4088616452368e14c4f8fbee56f3258ac7f5dd913 in /KEYS 
# Tue, 14 Aug 2018 12:03:26 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Tue, 14 Aug 2018 12:03:27 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Tue, 14 Aug 2018 12:03:27 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 14 Aug 2018 12:03:27 GMT
EXPOSE 6123/tcp 8081/tcp
# Tue, 14 Aug 2018 12:03:27 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:5483105d09166836731e940c850827dd1a4fe16b04d1921eea4d8da7c98e99bc`  
		Last Modified: Sat, 28 Apr 2018 12:15:18 GMT  
		Size: 42.1 MB (42063737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ed57f83cc7c78757972312a1b5a30524f861523c5390d062845f18c696f48ea`  
		Last Modified: Sat, 05 May 2018 12:35:37 GMT  
		Size: 9.5 MB (9472475 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:859203aede279201e8caf07cf2963456c56bac72a64071079dc9db6fb65ed1a2`  
		Last Modified: Sat, 05 May 2018 12:35:34 GMT  
		Size: 3.9 MB (3912835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df26ddf71ea9e82f175e400809b8f06871dd0937c5a90f4ffe95286544a9f719`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 830.3 KB (830332 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a2c21322a9c89724512d6ea5faa10299c60c8a605d6f563c84c28177db8d2770`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2270f04a4be61f52577232813fff92e797d3fc190d52f71411afc26b0911f8e4`  
		Last Modified: Sat, 05 May 2018 13:29:04 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da2dc1aba58c8cd285639cac6b03c823e5fcdb91aa8922652e7d9387aaca6fa4`  
		Last Modified: Sat, 05 May 2018 13:29:37 GMT  
		Size: 139.5 MB (139501760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02869ec2bb3864b06abd435610eb6849d5c62426517de1a603ef6fe43c7d3815`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 272.1 KB (272082 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71122e80751c26d15d17856e1659781f3e5297edf0aff11a2ede2ab486e0f4b8`  
		Last Modified: Fri, 20 Jul 2018 12:07:20 GMT  
		Size: 479.6 KB (479566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:232ceecfeba69d3dc2589b30cacd748fea414abd077deab71956424a2788d552`  
		Last Modified: Fri, 20 Jul 2018 12:07:21 GMT  
		Size: 761.9 KB (761883 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:618bc7830b04ddb28bbfedd2a43fedcea0649d59a197deffb954b03e99c3d526`  
		Last Modified: Tue, 14 Aug 2018 12:07:56 GMT  
		Size: 4.6 KB (4573 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2838518ceb2c1b83d9e4dd2c60c9d6e5ceb2c2536fc486eae94a3e426dcb1ccc`  
		Last Modified: Tue, 14 Aug 2018 12:07:56 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44a9bc455e939c3b441affcd275c7221c78b7c2b2a25b30da27df71405db7625`  
		Last Modified: Tue, 14 Aug 2018 12:07:55 GMT  
		Size: 59.3 KB (59336 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8aaba5598ed00524bd061366a4e3404584724e5d2a4869e7b7fdf2afa040699b`  
		Last Modified: Tue, 14 Aug 2018 12:08:24 GMT  
		Size: 265.5 MB (265460296 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b12f78824d00d6917789d927dcc66014b09dc5743980bd803db9e08fe72f223`  
		Last Modified: Tue, 14 Aug 2018 12:07:56 GMT  
		Size: 1.1 KB (1118 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `flink:scala_2.11` - linux; arm64 variant v8

```console
$ docker pull flink@sha256:3dde9030049b71cba8f57a07ec9135c0e4a722705c40e23aee253bed50d2b2bc
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **437.5 MB (437494733 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1a51a6ac487bea71edbcfd9c5b2f48b27bc77ebb24102c3e65c03093f0d6e3f4`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Tue, 17 Jul 2018 08:47:22 GMT
ADD file:5e1a1aab339b0b1e3047eeab5d0c6c74ad3f388d0407dc86f41e4a78b99c6fd8 in / 
# Tue, 17 Jul 2018 08:47:23 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:51:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:52:06 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 20:24:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 20:24:55 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 20:24:59 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 20:25:03 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 20:25:04 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 09:27:47 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 09:27:48 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 09:27:49 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 09:32:01 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 09:32:06 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 10:45:07 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 10:45:23 GMT
ENV GOSU_VERSION=1.7
# Wed, 15 Aug 2018 10:45:30 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Wed, 15 Aug 2018 11:06:15 GMT
ENV FLINK_VERSION=1.6.0 HADOOP_SCALA_VARIANT=scala_2.11
# Wed, 15 Aug 2018 11:06:16 GMT
ENV FLINK_HOME=/opt/flink
# Wed, 15 Aug 2018 11:06:17 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 15 Aug 2018 11:06:20 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Wed, 15 Aug 2018 11:06:21 GMT
WORKDIR /opt/flink
# Wed, 15 Aug 2018 11:06:21 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz
# Wed, 15 Aug 2018 11:06:22 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz.asc
# Wed, 15 Aug 2018 11:06:23 GMT
COPY file:d9b980b40ddcfab2700a72e4088616452368e14c4f8fbee56f3258ac7f5dd913 in /KEYS 
# Wed, 15 Aug 2018 11:08:05 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Wed, 15 Aug 2018 11:08:12 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Wed, 15 Aug 2018 11:08:12 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 15 Aug 2018 11:08:13 GMT
EXPOSE 6123/tcp 8081/tcp
# Wed, 15 Aug 2018 11:08:14 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:24e48664c69560cde9534aadde23364122f1feb02b5db0ab3776983a4788ea63`  
		Last Modified: Tue, 17 Jul 2018 08:56:03 GMT  
		Size: 43.1 MB (43123568 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbcf842c718cc953be45905967fc6a0114f55314ce412b80107e20d8b43fdcdb`  
		Last Modified: Tue, 17 Jul 2018 15:10:44 GMT  
		Size: 9.7 MB (9690273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:317d79a9c0a5c766d03c1c253fa09f645ed7321dc3a80e0ae33599958677cd1d`  
		Last Modified: Tue, 17 Jul 2018 15:10:41 GMT  
		Size: 4.1 MB (4088491 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f34353c71abcb0a3423640b466779e00b7da4d2d4ebcdd89f3611d4c936b14ef`  
		Last Modified: Tue, 17 Jul 2018 20:53:29 GMT  
		Size: 839.2 KB (839215 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11a58de95103410c7614c07fbfbd2339f5b6657abdb8d847198c246eb1d753e3`  
		Last Modified: Tue, 17 Jul 2018 20:53:30 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:523b8fda53cc2bfd5306eedc221a547f3dd09df4aa2eeb8b0a72da68eace3c68`  
		Last Modified: Tue, 17 Jul 2018 20:53:29 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf4fd39dafb9ad45f57c89125992e8197ddf2b218db872801723f2f7f9c0d9e5`  
		Last Modified: Wed, 15 Aug 2018 09:42:17 GMT  
		Size: 112.7 MB (112749799 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df7e84d92bb0c762009e72f6bcebe6327697bba2477ece3bf08ad63e7b8dce4f`  
		Last Modified: Wed, 15 Aug 2018 09:41:41 GMT  
		Size: 246.7 KB (246667 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2a28f3aa23b307c1b098631c9d9e5763f53c7e142da84cac8f5570c166ccf6e`  
		Last Modified: Wed, 15 Aug 2018 11:16:45 GMT  
		Size: 466.6 KB (466605 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:130609ccaaea1242425fd7d64fdc5fb29b2aea340344271eee22cc0eaad76b26`  
		Last Modified: Wed, 15 Aug 2018 11:16:45 GMT  
		Size: 764.4 KB (764408 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0c78f1fef2ae93aaee9dcb4168fd54893555d28d06e6b6a667b90373cbe3297`  
		Last Modified: Wed, 15 Aug 2018 11:35:12 GMT  
		Size: 4.6 KB (4647 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:555b31e08f4ce9107d0657836ef7782808c5bf6282df19d3c32e43748c804e89`  
		Last Modified: Wed, 15 Aug 2018 11:35:12 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed4a841d94b862d8991e8c93f3fd7d8eb06d6c537cf1cc1ddc3a5a6d2fb34261`  
		Last Modified: Wed, 15 Aug 2018 11:35:13 GMT  
		Size: 59.3 KB (59338 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a20f7e6179ab041cdeeae25c58ca8c6a11aefa0ce8234e748575a27d82c8164`  
		Last Modified: Wed, 15 Aug 2018 11:35:48 GMT  
		Size: 265.5 MB (265460113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f7ca68435c293d12b4a0b273890106b841e4e587d48a6511a9996a429ea53a9`  
		Last Modified: Wed, 15 Aug 2018 11:35:13 GMT  
		Size: 1.1 KB (1117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `flink:scala_2.11` - linux; 386

```console
$ docker pull flink@sha256:af7df5d80b60de47b2b985f878bf57b86a95feecb62bec92e99aa238042e926a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **451.8 MB (451821778 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f4b8a3cd83eae51aee033c6de3f4cf90d71ed8c9fe324c3dc47cd59e6b0282e8`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Tue, 17 Jul 2018 10:49:17 GMT
ADD file:be09029a70a8ca76c88918bd3070fb0cbd97606c95450ec1d27efa9f78536d6f in / 
# Tue, 17 Jul 2018 10:49:20 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:34:44 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:34:55 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 18:17:47 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 18:17:47 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 18:17:48 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 18:17:49 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 18:17:49 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 11:06:46 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 11:06:46 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 11:06:46 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 11:07:41 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 11:07:45 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 12:48:27 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 12:48:27 GMT
ENV GOSU_VERSION=1.7
# Wed, 15 Aug 2018 12:48:33 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Wed, 15 Aug 2018 12:58:42 GMT
ENV FLINK_VERSION=1.6.0 HADOOP_SCALA_VARIANT=scala_2.11
# Wed, 15 Aug 2018 12:58:42 GMT
ENV FLINK_HOME=/opt/flink
# Wed, 15 Aug 2018 12:58:42 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 15 Aug 2018 12:58:43 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Wed, 15 Aug 2018 12:58:43 GMT
WORKDIR /opt/flink
# Wed, 15 Aug 2018 12:58:44 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz
# Wed, 15 Aug 2018 12:58:44 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz.asc
# Wed, 15 Aug 2018 12:58:44 GMT
COPY file:d9b980b40ddcfab2700a72e4088616452368e14c4f8fbee56f3258ac7f5dd913 in /KEYS 
# Wed, 15 Aug 2018 13:00:53 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Wed, 15 Aug 2018 13:01:04 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Wed, 15 Aug 2018 13:01:04 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 15 Aug 2018 13:01:05 GMT
EXPOSE 6123/tcp 8081/tcp
# Wed, 15 Aug 2018 13:01:05 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:79324aeae468dc95e9d1ad7d17eccb16f424671f297c1c8231f48ad8b2a5a949`  
		Last Modified: Tue, 17 Jul 2018 11:07:28 GMT  
		Size: 46.0 MB (46037522 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d55059f59399b1edb44f6fccf01b4b41c46365022205a35f92fa4aee831f1bac`  
		Last Modified: Tue, 17 Jul 2018 15:15:31 GMT  
		Size: 10.8 MB (10752710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b748c8a9e197a5c36217dc0236e60923d398eef3c44073cffeed563cb61421c3`  
		Last Modified: Tue, 17 Jul 2018 15:15:28 GMT  
		Size: 4.6 MB (4555355 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3087334993bfdb6aa03f8ed812f7ae6285de6d3ee1e641556605f833bbce1659`  
		Last Modified: Tue, 17 Jul 2018 18:49:51 GMT  
		Size: 861.8 KB (861753 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04203d47c665fca1d30763face2370a9dff9ca3660fecf95d8d4714b48b65a38`  
		Last Modified: Tue, 17 Jul 2018 18:49:51 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75b367c5a41976187a4e0c9aa9bb164c3adda20df48f0023fb68e0c069249cde`  
		Last Modified: Tue, 17 Jul 2018 18:49:52 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bc0944cc675b368c9bc075d2777a3d19a87fd1c15bc5867c7f5fad19f52bd61`  
		Last Modified: Wed, 15 Aug 2018 11:19:47 GMT  
		Size: 122.6 MB (122591471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cafd3f294bd9b99066131f86718f42153ca53a3051682c2d1db7f035cd4766f`  
		Last Modified: Wed, 15 Aug 2018 11:19:05 GMT  
		Size: 246.7 KB (246725 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4be1d56d43fb1647a06e934d50f5342bd531e2f092499d63534d552639e00d99`  
		Last Modified: Wed, 15 Aug 2018 13:02:08 GMT  
		Size: 467.6 KB (467558 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9af73e8d4596cb2d6df95f47b8eaec6cdfdbca3d5d07e0abc36b38312971c762`  
		Last Modified: Wed, 15 Aug 2018 13:02:10 GMT  
		Size: 783.1 KB (783089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b6927c3d0bf9bf3dac8706d69b3e3c77de4ecd60c948aa9f14f976fe508bfad`  
		Last Modified: Wed, 15 Aug 2018 13:21:04 GMT  
		Size: 4.5 KB (4534 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2f593bdbfd0035da74db68ad68b94002d81ad95e24c9052ff02ba8410c7c602`  
		Last Modified: Wed, 15 Aug 2018 13:21:04 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dff724593569db53fc9f333f2b0daded903225fe981c51c8843d24292afd9702`  
		Last Modified: Wed, 15 Aug 2018 13:21:05 GMT  
		Size: 59.3 KB (59338 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8366d20cc66c52b35ac3f6cbed73c659d136bcd8ffc742b503a170761478537`  
		Last Modified: Wed, 15 Aug 2018 13:21:34 GMT  
		Size: 265.5 MB (265460113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43e226bd1969bd7fb92349c0033e5248b99fd37f383a0e7ec3c54138456a9374`  
		Last Modified: Wed, 15 Aug 2018 13:21:04 GMT  
		Size: 1.1 KB (1117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `flink:scala_2.11` - linux; ppc64le

```console
$ docker pull flink@sha256:7304b34204f87fa5ace704610da2e5228a0601fdf71dea0e1ed41bcf249a39b3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **442.2 MB (442220804 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9506d436b989784d2f3a5d6cfdb4c6844bf3b273b8112faa6a6af05cf99d3b45`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Tue, 17 Jul 2018 08:20:06 GMT
ADD file:692c439870d267b1a84ee3f6c44eb8a4a8342eef759391242613964e31747b24 in / 
# Tue, 17 Jul 2018 08:20:07 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:10:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:11:29 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 17:14:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 17:14:37 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 17:14:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 17:14:42 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 17:14:42 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 15 Aug 2018 09:45:12 GMT
ENV JAVA_VERSION=8u181
# Wed, 15 Aug 2018 09:45:14 GMT
ENV JAVA_DEBIAN_VERSION=8u181-b13-1~deb9u1
# Wed, 15 Aug 2018 09:45:15 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 15 Aug 2018 09:49:35 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 15 Aug 2018 09:49:43 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 15 Aug 2018 11:56:05 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Wed, 15 Aug 2018 11:56:11 GMT
ENV GOSU_VERSION=1.7
# Wed, 15 Aug 2018 11:56:35 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Wed, 15 Aug 2018 12:27:06 GMT
ENV FLINK_VERSION=1.6.0 HADOOP_SCALA_VARIANT=scala_2.11
# Wed, 15 Aug 2018 12:27:07 GMT
ENV FLINK_HOME=/opt/flink
# Wed, 15 Aug 2018 12:27:09 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 15 Aug 2018 12:27:13 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Wed, 15 Aug 2018 12:27:16 GMT
WORKDIR /opt/flink
# Wed, 15 Aug 2018 12:27:18 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz
# Wed, 15 Aug 2018 12:27:19 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.6.0/flink-1.6.0-bin-scala_2.11.tgz.asc
# Wed, 15 Aug 2018 12:27:21 GMT
COPY file:d9b980b40ddcfab2700a72e4088616452368e14c4f8fbee56f3258ac7f5dd913 in /KEYS 
# Wed, 15 Aug 2018 12:29:55 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Wed, 15 Aug 2018 12:29:57 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Wed, 15 Aug 2018 12:29:58 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 15 Aug 2018 12:29:59 GMT
EXPOSE 6123/tcp 8081/tcp
# Wed, 15 Aug 2018 12:30:02 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:4d37f09838fa8757d02699f103191e672c0ecde0fcf23bb3706d1343831762fb`  
		Last Modified: Tue, 17 Jul 2018 08:25:32 GMT  
		Size: 45.6 MB (45594057 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22b62820a77d74ffab7785bdebc26e90a2ad429b6a23be61002b575c308f717e`  
		Last Modified: Tue, 17 Jul 2018 14:16:47 GMT  
		Size: 9.9 MB (9943597 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b71a75676a8f5e4b583626a0edc6859aa782e4d90d17995e1e8251146eedfbe4`  
		Last Modified: Tue, 17 Jul 2018 14:16:45 GMT  
		Size: 4.3 MB (4290027 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4415e630df1874ff5d01fdfd39e6dd1daf0d79e810326feedc8d715cd280882d`  
		Last Modified: Tue, 17 Jul 2018 17:42:54 GMT  
		Size: 848.5 KB (848525 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:214a97408c8c4458ef417c27d1d27b63afa6b96f8849073d3493df09ce7030b3`  
		Last Modified: Tue, 17 Jul 2018 17:42:53 GMT  
		Size: 246.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39ffc60b9a164d01c0612e2cba6587ea3ce873cfa01f69534f141df3753c060e`  
		Last Modified: Tue, 17 Jul 2018 17:42:52 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:514b9d8bb874828e28fce366031a3e6c5f730c65a3c7a81c9ec38da819485cfa`  
		Last Modified: Wed, 15 Aug 2018 09:57:17 GMT  
		Size: 114.5 MB (114536687 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a92ef98a1f301e29ad3bc8916a74dc4577aa3fc2bb6b7291a87626a250f0495`  
		Last Modified: Wed, 15 Aug 2018 09:56:46 GMT  
		Size: 246.8 KB (246751 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d26c135cf47fb955515fd5669c594e98acce558ad9b094ed9bde4040f3e01204`  
		Last Modified: Wed, 15 Aug 2018 12:31:20 GMT  
		Size: 468.4 KB (468382 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:817639ea472199b437357e7031f6643543c6d8326d48bbc1a0ac3fc521f61854`  
		Last Modified: Wed, 15 Aug 2018 12:31:20 GMT  
		Size: 767.0 KB (766993 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d09d267ae05e82305deb5dc0686e3ef7c8dbdfb1cde731d1ff7f71903062f03`  
		Last Modified: Wed, 15 Aug 2018 12:45:55 GMT  
		Size: 4.6 KB (4620 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca798ddfb829c7977571c8cc88f299ac8a2bbabff2f4c018d2a5aa5799799467`  
		Last Modified: Wed, 15 Aug 2018 12:45:54 GMT  
		Size: 147.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c258cb19dd906cfbdccd5298ab6bd8c4b48d4c6fe304196003ff6dd1c2177853`  
		Last Modified: Wed, 15 Aug 2018 12:45:54 GMT  
		Size: 59.3 KB (59337 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8844c8ea470595df7cda824a06aee4f2251c87ca0062c2541b4d4254a4fdeeb2`  
		Last Modified: Wed, 15 Aug 2018 12:46:25 GMT  
		Size: 265.5 MB (265460186 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:548704b8fb2d5d1d3be1f5763b490431873c7a99f2c824bb55091383b25128a9`  
		Last Modified: Wed, 15 Aug 2018 12:45:54 GMT  
		Size: 1.1 KB (1117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
