## `spiped:alpine`

```console
$ docker pull spiped@sha256:1c7b8430bfa12786d70b6619a52c27139bb7c27b59f9f3451e5eccaaeeb0b583
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `spiped:alpine` - linux; amd64

```console
$ docker pull spiped@sha256:58653738b045679a8daf3fbd4cf3558a3e32e0aa0d6346215ac4ed2d7e43b497
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.9 MB (4863459 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f5a1cb874da6f5ad39c265e642982053a52fd955397fe2ed75c7813480f6289c`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Fri, 06 Jul 2018 14:14:06 GMT
ADD file:25f61d70254b9807a40cd3e8d820f6a5ec0e1e596de04e325f6a33810393e95a in / 
# Fri, 06 Jul 2018 14:14:06 GMT
CMD ["/bin/sh"]
# Sat, 07 Jul 2018 03:42:49 GMT
RUN addgroup -S spiped &&	adduser -S -G spiped spiped
# Sat, 07 Jul 2018 03:42:50 GMT
RUN apk add --no-cache libssl1.0
# Sat, 07 Jul 2018 03:42:50 GMT
ENV SPIPED_VERSION=1.6.0
# Sat, 07 Jul 2018 03:42:51 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Sat, 07 Jul 2018 03:42:51 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Sat, 07 Jul 2018 03:43:09 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 		curl 		gcc 		make 		musl-dev 		openssl-dev 		tar &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 *spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	CC=gcc make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apk del .build-deps
# Sat, 07 Jul 2018 03:43:09 GMT
VOLUME [/spiped]
# Sat, 07 Jul 2018 03:43:10 GMT
WORKDIR /spiped
# Sat, 07 Jul 2018 03:43:10 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Sat, 07 Jul 2018 03:43:10 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 07 Jul 2018 03:43:11 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:8e3ba11ec2a2b39ab372c60c16b421536e50e5ce64a0bc81765c2e38381bcff6`  
		Last Modified: Fri, 06 Jul 2018 04:15:58 GMT  
		Size: 2.2 MB (2206542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:238308f783528935eca9ccb7cf50ae56a4d944e583b97bc00d1ab1440c4f53aa`  
		Last Modified: Sat, 07 Jul 2018 03:43:30 GMT  
		Size: 1.2 KB (1248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fb0657f0bdfcf5044dc8bfec89a096b0ac39890edfe90b0adfbfd80e70c0499`  
		Last Modified: Sat, 07 Jul 2018 03:43:30 GMT  
		Size: 1.3 MB (1301303 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4804da4f6a19c174657eff6fed7fd178acb552ad3bcb89d9444990b346989be7`  
		Last Modified: Sat, 07 Jul 2018 03:43:30 GMT  
		Size: 1.4 MB (1353931 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81b8c54b0d601a174cbf1544e8880ef0dcfc1f3a849e08a2b83139d489b663ed`  
		Last Modified: Sat, 07 Jul 2018 03:43:29 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d44d299a7626245569fa232bd8637fd1d6dc7c6277e254324db773bad8e7eba7`  
		Last Modified: Sat, 07 Jul 2018 03:43:29 GMT  
		Size: 340.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:alpine` - linux; arm variant v6

```console
$ docker pull spiped@sha256:a97ca052bd4d4d5ace0c6ddc823b194c02318797af3b58530378b546025f04ab
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.4 MB (4365863 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e141a81d2d7ef9cabdc6fa8bfb7928fafbb49b19824a4b8a90c3c81669d59185`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Fri, 06 Jul 2018 07:53:29 GMT
ADD file:122e3422d9afa971806601812374fdd9d00c8edc8e9a6df7256e2caa85fab6d1 in / 
# Fri, 06 Jul 2018 07:53:30 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 07:53:30 GMT
CMD ["/bin/sh"]
# Sat, 14 Jul 2018 12:01:17 GMT
RUN addgroup -S spiped &&	adduser -S -G spiped spiped
# Sat, 14 Jul 2018 12:01:23 GMT
RUN apk add --no-cache libssl1.0
# Sat, 14 Jul 2018 12:01:24 GMT
ENV SPIPED_VERSION=1.6.0
# Sat, 14 Jul 2018 12:01:24 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Sat, 14 Jul 2018 12:01:25 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Sat, 14 Jul 2018 12:03:33 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 		curl 		gcc 		make 		musl-dev 		openssl-dev 		tar &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 *spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	CC=gcc make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apk del .build-deps
# Sat, 14 Jul 2018 12:03:34 GMT
VOLUME [/spiped]
# Sat, 14 Jul 2018 12:03:35 GMT
WORKDIR /spiped
# Sat, 14 Jul 2018 12:03:36 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Sat, 14 Jul 2018 12:03:37 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 14 Jul 2018 12:03:38 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:ee7d700abbf209aa401ef5d53f86af298a25e8154b3259036e9307d08f255c5d`  
		Last Modified: Fri, 06 Jul 2018 07:53:45 GMT  
		Size: 2.1 MB (2145998 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1653f4692c1ccea69cd46121d4f1371957f66e97a20141371dd4da10ebaec19`  
		Last Modified: Fri, 06 Jul 2018 07:53:45 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d83edd4c68cca51d3c254f9fdf3fb55cf21a95431a5806fe5d59336c4e9e135`  
		Last Modified: Sat, 14 Jul 2018 12:04:01 GMT  
		Size: 1.3 KB (1278 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c2349b96c595a764e625e89ca3e146228fe1019d35f37d77b830461157e269e`  
		Last Modified: Sat, 14 Jul 2018 12:04:03 GMT  
		Size: 911.5 KB (911532 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1254c85dca454cf68f0060cfbd9aeae3a68035266dfb3b373dd18f4fe01a740d`  
		Last Modified: Sat, 14 Jul 2018 12:04:02 GMT  
		Size: 1.3 MB (1306411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3646961dc71115b0d647845430e27b29c6ee4c1991a4252967e4f5b17fd87770`  
		Last Modified: Sat, 14 Jul 2018 12:04:02 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:815ff7030fcef9941864ea919914b4a966114a7aed9fbeaf034f5dd41248cf09`  
		Last Modified: Sat, 14 Jul 2018 12:04:02 GMT  
		Size: 340.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:alpine` - linux; arm64 variant v8

```console
$ docker pull spiped@sha256:ba04fcad828001876151273e768706f9b134c14fd6eae5aeb5df1b893774add6
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.3 MB (4338695 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8f044bfc751a658779b28631bd81f1bef44d8e0f731ab299c41ceaf37e113580`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Fri, 06 Jul 2018 08:41:03 GMT
ADD file:199a5a48bddabaf1f649f58f3b17c323a1aa1a50e939dfdea3542e4041e91b7b in / 
# Fri, 06 Jul 2018 08:41:03 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 08:41:04 GMT
CMD ["/bin/sh"]
# Sat, 07 Jul 2018 09:38:14 GMT
RUN addgroup -S spiped &&	adduser -S -G spiped spiped
# Sat, 07 Jul 2018 09:38:16 GMT
RUN apk add --no-cache libssl1.0
# Sat, 07 Jul 2018 09:38:17 GMT
ENV SPIPED_VERSION=1.6.0
# Sat, 07 Jul 2018 09:38:18 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Sat, 07 Jul 2018 09:38:19 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Sat, 07 Jul 2018 09:38:43 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 		curl 		gcc 		make 		musl-dev 		openssl-dev 		tar &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 *spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	CC=gcc make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apk del .build-deps
# Sat, 07 Jul 2018 09:38:43 GMT
VOLUME [/spiped]
# Sat, 07 Jul 2018 09:38:44 GMT
WORKDIR /spiped
# Sat, 07 Jul 2018 09:38:45 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Sat, 07 Jul 2018 09:38:46 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 07 Jul 2018 09:38:47 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:47e04371c99027fae42871b720fdc6cdddcb65062bfa05f0c3bb0a594cb5bbbd`  
		Last Modified: Wed, 27 Jun 2018 19:15:35 GMT  
		Size: 2.1 MB (2099514 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4103359e1ecd9a7253d8b8a041d4e81db1ff4a5e1950bc0e02305d221c9e6c2`  
		Last Modified: Fri, 06 Jul 2018 08:42:09 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9192df97a42e9ed4d42332071bd5e9eafce9e438f3c3a7509a6d1c41211ea902`  
		Last Modified: Sat, 07 Jul 2018 09:39:09 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc0626024507b4dd65535391cd2519db24bc4d171f98f7eba5c908762cea690d`  
		Last Modified: Sat, 07 Jul 2018 09:39:10 GMT  
		Size: 926.9 KB (926924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1dfb36cda8fb398aa534be75a3c8cf8831ac296c808452c6ded06e43ddb8b2cd`  
		Last Modified: Sat, 07 Jul 2018 09:39:09 GMT  
		Size: 1.3 MB (1310398 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d6d3a605fdd263436a1b55e3d4f1459dd0194b62a0813cce081ed9efcfd0e1b`  
		Last Modified: Sat, 07 Jul 2018 09:39:09 GMT  
		Size: 93.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d6bd7834c456e9f0b3277dbac99dd5f153773d8b4e09b4a44b5127a6781341f`  
		Last Modified: Sat, 07 Jul 2018 09:39:09 GMT  
		Size: 340.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:alpine` - linux; 386

```console
$ docker pull spiped@sha256:ffc0a09248953c9b1c251679b70c2f0feca2aadb9ba6331daa6cd460289a7307
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.7 MB (4738874 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5b41ce4be0e2b2d204f4b3fec4a14390474af6f01ea29d8b4bedfd994b154d59`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Fri, 06 Jul 2018 15:02:06 GMT
ADD file:ebd40cda2f6087daf4d14e6dc1ee0b4a0fb5dc96c70129be8e07de0e5c628312 in / 
# Fri, 06 Jul 2018 15:02:07 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 15:02:07 GMT
CMD ["/bin/sh"]
# Sat, 07 Jul 2018 11:00:54 GMT
RUN addgroup -S spiped &&	adduser -S -G spiped spiped
# Sat, 07 Jul 2018 11:00:57 GMT
RUN apk add --no-cache libssl1.0
# Sat, 07 Jul 2018 11:00:57 GMT
ENV SPIPED_VERSION=1.6.0
# Sat, 07 Jul 2018 11:00:57 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Sat, 07 Jul 2018 11:00:57 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Sat, 07 Jul 2018 11:01:14 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 		curl 		gcc 		make 		musl-dev 		openssl-dev 		tar &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 *spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	CC=gcc make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apk del .build-deps
# Sat, 07 Jul 2018 11:01:15 GMT
VOLUME [/spiped]
# Sat, 07 Jul 2018 11:01:15 GMT
WORKDIR /spiped
# Sat, 07 Jul 2018 11:01:15 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Sat, 07 Jul 2018 11:01:16 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 07 Jul 2018 11:01:16 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:ef15772113129a5330876ce10683bbf6509a4c4c99b3a99894dcbc7560975052`  
		Last Modified: Fri, 06 Jul 2018 15:02:46 GMT  
		Size: 2.3 MB (2270920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6df692b84cf35e6038d677f9ab7de2a3c671c57671043da1d20d99252e0d9c42`  
		Last Modified: Fri, 06 Jul 2018 15:02:43 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a058f5a1285e67e9755ef2057609e32bf07c04d8eec0a3f85dbd30670938be2`  
		Last Modified: Sat, 07 Jul 2018 11:01:30 GMT  
		Size: 1.2 KB (1248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:812eac6a861ee484c7258b7409dc00feb6e1cd0e7ef7d4e669ac99435473dc58`  
		Last Modified: Sat, 07 Jul 2018 11:01:30 GMT  
		Size: 1.1 MB (1123893 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0bab8ba5a8e875cdb4675f57c4bad389edb17f000b05c62fcba75eee48e0bf0`  
		Last Modified: Sat, 07 Jul 2018 11:01:30 GMT  
		Size: 1.3 MB (1342201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:288d75a5f4b1229bbe9f78889cb7d3da73f15330d0582c11be65ab8d422b453a`  
		Last Modified: Sat, 07 Jul 2018 11:01:30 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea103e55de7be25e2dd08b1acde00acd79f48f44cd9fd71f7278544b42a6b0cd`  
		Last Modified: Sat, 07 Jul 2018 11:01:30 GMT  
		Size: 342.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:alpine` - linux; ppc64le

```console
$ docker pull spiped@sha256:7fd76f31713643fc8968b92ac6dfb9da432648c2dde5ca22498a80051fb25e59
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.5 MB (4517734 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cd0d7d214cfac1ae7ac46f866f052edb7d50431f62cc9e7ed3daaa9b53661eec`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Fri, 06 Jul 2018 08:18:09 GMT
ADD file:4ff20d593b16518d45b1b1d6efdab141199316dba7a53ce7459249f5de690dfd in / 
# Fri, 06 Jul 2018 08:18:10 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 08:18:11 GMT
CMD ["/bin/sh"]
# Sat, 07 Jul 2018 08:53:30 GMT
RUN addgroup -S spiped &&	adduser -S -G spiped spiped
# Sat, 07 Jul 2018 08:53:34 GMT
RUN apk add --no-cache libssl1.0
# Sat, 07 Jul 2018 08:53:35 GMT
ENV SPIPED_VERSION=1.6.0
# Sat, 07 Jul 2018 08:53:36 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Sat, 07 Jul 2018 08:53:37 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Sat, 07 Jul 2018 08:53:58 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 		curl 		gcc 		make 		musl-dev 		openssl-dev 		tar &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 *spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	CC=gcc make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apk del .build-deps
# Sat, 07 Jul 2018 08:54:01 GMT
VOLUME [/spiped]
# Sat, 07 Jul 2018 08:54:03 GMT
WORKDIR /spiped
# Sat, 07 Jul 2018 08:54:07 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Sat, 07 Jul 2018 08:54:08 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 07 Jul 2018 08:54:10 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:e642bcb5b1890a07dd2fc8be2bc35edf5e2b651d4993e71caef03b4b43ace970`  
		Last Modified: Fri, 06 Jul 2018 08:18:44 GMT  
		Size: 2.2 MB (2194861 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e09410b1fce4c4630b3bc57c6ee158ee9821ec415d0acaa1607b9e0bcf76d91`  
		Last Modified: Fri, 06 Jul 2018 08:18:43 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12dfbdbfa83decaaebba31bb3d6aba694ad7db2a9fdb88ddf0c4beabcc19edd1`  
		Last Modified: Sat, 07 Jul 2018 08:54:32 GMT  
		Size: 1.3 KB (1279 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ea4c6854013a40004d988f636b60fbe119801143a54b89b2f13e3fb1934ceae`  
		Last Modified: Sat, 07 Jul 2018 08:54:33 GMT  
		Size: 996.9 KB (996894 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48f8a5b96139a61a87d6b207aee87325a3fe58d57188d075801de843fcb6b755`  
		Last Modified: Sat, 07 Jul 2018 08:54:33 GMT  
		Size: 1.3 MB (1324053 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:406eac5385a9d91d424e301b947a87650f16ee1e83079c2cf534312385090c4c`  
		Last Modified: Sat, 07 Jul 2018 08:54:32 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68725a2bc1cea1b526f696f61d5334c1dfae5cf3207b528f4f462d02c49b8faf`  
		Last Modified: Sat, 07 Jul 2018 08:54:33 GMT  
		Size: 342.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `spiped:alpine` - linux; s390x

```console
$ docker pull spiped@sha256:d96e6aa529decc50d4dac5e10de2649ef20d2785f68e1d474fc89d536b033b01
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.7 MB (4657142 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:80c7f1766812109fbf54809b551e56d88066dc4d69a5d58657ad7bb06915f78f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["spiped"]`

```dockerfile
# Fri, 06 Jul 2018 11:41:42 GMT
ADD file:376dd7fc34ad39570d2e20f3704305e788ae613c589445b3e8fb880147c3eb59 in / 
# Fri, 06 Jul 2018 11:41:43 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 06 Jul 2018 11:41:43 GMT
CMD ["/bin/sh"]
# Sat, 07 Jul 2018 12:06:27 GMT
RUN addgroup -S spiped &&	adduser -S -G spiped spiped
# Sat, 07 Jul 2018 12:06:28 GMT
RUN apk add --no-cache libssl1.0
# Sat, 07 Jul 2018 12:06:28 GMT
ENV SPIPED_VERSION=1.6.0
# Sat, 07 Jul 2018 12:06:29 GMT
ENV SPIPED_DOWNLOAD_URL=https://www.tarsnap.com/spiped/spiped-1.6.0.tgz
# Sat, 07 Jul 2018 12:06:29 GMT
ENV SPIPED_DOWNLOAD_SHA256=e6f7f8f912172c3ad55638af8346ae7c4ecaa92aed6d3fb60f2bda4359cba1e4
# Sat, 07 Jul 2018 12:06:38 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 		curl 		gcc 		make 		musl-dev 		openssl-dev 		tar &&	curl -fsSL "$SPIPED_DOWNLOAD_URL" -o spiped.tar.gz &&	echo "$SPIPED_DOWNLOAD_SHA256 *spiped.tar.gz" |sha256sum -c - &&	mkdir -p /usr/local/src/spiped &&	tar xzf "spiped.tar.gz" -C /usr/local/src/spiped --strip-components=1 &&	rm "spiped.tar.gz" &&	CC=gcc make -C /usr/local/src/spiped &&	make -C /usr/local/src/spiped install &&	rm -rf /usr/local/src/spiped &&	apk del .build-deps
# Sat, 07 Jul 2018 12:06:38 GMT
VOLUME [/spiped]
# Sat, 07 Jul 2018 12:06:38 GMT
WORKDIR /spiped
# Sat, 07 Jul 2018 12:06:39 GMT
COPY multi:cece67136bcb3e9eb15d965c7f2f0aa1577fa83acbd640e2016eb71cc01e0cfa in /usr/local/bin/ 
# Sat, 07 Jul 2018 12:06:39 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 07 Jul 2018 12:06:39 GMT
CMD ["spiped"]
```

-	Layers:
	-	`sha256:cdf21ace94188d512903eea53ea8559677e0e6ffd5d6a180a1d88c118abc96fc`  
		Last Modified: Fri, 06 Jul 2018 11:42:01 GMT  
		Size: 2.3 MB (2307471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea178433f2f09080fbbf77f09da1b16d588b7ced380d495a2f2ad00d28468338`  
		Last Modified: Fri, 06 Jul 2018 11:42:00 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1e070e770633a2b5db7e68d037725a846fe6fe9be06f842c3e4bd4fa5f916b0`  
		Last Modified: Sat, 07 Jul 2018 12:06:52 GMT  
		Size: 1.3 KB (1251 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dc1ae2f3d0f10e94ed98029005f70f55e447eb7e4a7256f1f35b6ad2f4665ab8`  
		Last Modified: Sat, 07 Jul 2018 12:06:53 GMT  
		Size: 1.1 MB (1062585 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da8d818bf2817431d08018b3cc25298c25d38de8878badca16de0ec4e51b710a`  
		Last Modified: Sat, 07 Jul 2018 12:06:54 GMT  
		Size: 1.3 MB (1285224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e1083cecbc0ed03e82596754021312dd318a69b4c9a86d79e14e193f90eef8e`  
		Last Modified: Sat, 07 Jul 2018 12:06:52 GMT  
		Size: 95.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc8f2f752a945d183a9f9cf79680bf9d86143bd1e34db5904f8e78acf6ec9bbb`  
		Last Modified: Sat, 07 Jul 2018 12:06:52 GMT  
		Size: 341.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
