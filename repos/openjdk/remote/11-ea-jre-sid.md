## `openjdk:11-ea-jre-sid`

```console
$ docker pull openjdk@sha256:8e837e0216bf70140b9a50c58753f67d929d418595c99a3290209e8abeea31d0
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `openjdk:11-ea-jre-sid` - linux; amd64

```console
$ docker pull openjdk@sha256:6d014f63b88b951eb059fc4c7aa95c02874beaccc434f236f28763c221fee07e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **246.4 MB (246353022 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d8cd3104d107f3461049f9ffdf843e17fbabe166924243ec69f024386d4fde2`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 00:24:39 GMT
ADD file:f04b64a73c29541d70cda855be7033dbd8e0b173ab11cd93458f3400fd270d85 in / 
# Tue, 17 Jul 2018 00:24:40 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 03:09:48 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 03:09:58 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 06:10:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:10:56 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:10:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:10:58 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:10:58 GMT
ENV JAVA_HOME=/docker-java-home
# Fri, 27 Jul 2018 22:24:24 GMT
ENV JAVA_VERSION=11-ea+24
# Fri, 27 Jul 2018 22:24:24 GMT
ENV JAVA_DEBIAN_VERSION=11~24-1
# Fri, 27 Jul 2018 22:25:23 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:e367ac4072dc48836ab52faeb39e943b075e21aa02c1a88f838651b9b384de50`  
		Last Modified: Tue, 17 Jul 2018 00:39:42 GMT  
		Size: 48.7 MB (48725588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a57779b5dbaefdeb5306372ffa77aee257957dd74042f9ea2572052c5cc9201`  
		Last Modified: Tue, 17 Jul 2018 03:50:25 GMT  
		Size: 7.0 MB (7035962 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a4c28c5ff25d086ba826711dd56a6652542b6dd75f3c5a4bb6daa1c8977bf7e`  
		Last Modified: Tue, 17 Jul 2018 03:50:27 GMT  
		Size: 9.2 MB (9245784 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9958359a5d4a9f92272abb0c2d50cf7dc8b5675ce88e82891d92c9115b13a474`  
		Last Modified: Tue, 17 Jul 2018 06:36:33 GMT  
		Size: 847.0 KB (847006 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d0448522bedd30888da1a520e7325d88a47e0702c1df4dc74aded42283506df`  
		Last Modified: Tue, 17 Jul 2018 06:36:32 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8c37e2c6a4d97d3ef881e59587132dff38d85bae29ea0fd3d1dd316a75d4b2a`  
		Last Modified: Tue, 17 Jul 2018 06:36:33 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:010c22855e48684f7e64f2094c29549684c2a75345a0577a7275ed9aea36a91c`  
		Last Modified: Fri, 27 Jul 2018 22:39:42 GMT  
		Size: 180.5 MB (180498315 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:11-ea-jre-sid` - linux; arm variant v5

```console
$ docker pull openjdk@sha256:c365d2dfbcaf28522704c37c514268979a04ccdb9d9c8ee45b3e6c813e59e3eb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **224.5 MB (224456608 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:949a0585827403636a91a8c5f52f0415a4b90e6d4a357362d71e72854657b748`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:53:54 GMT
ADD file:feed6b12801621af72a787e98590f6fd783022a609efc8254532712521e6c570 in / 
# Tue, 17 Jul 2018 08:53:55 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:46:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 11:46:22 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 12:35:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:35:12 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 12:35:13 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 12:35:15 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:35:15 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 28 Jul 2018 08:51:37 GMT
ENV JAVA_VERSION=11-ea+24
# Sat, 28 Jul 2018 08:51:37 GMT
ENV JAVA_DEBIAN_VERSION=11~24-1
# Sat, 28 Jul 2018 08:52:36 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:b6112397569f950be7cab355fd3cb9fb3b089c080499c1eebc269ecb7cc3715c`  
		Last Modified: Tue, 17 Jul 2018 09:06:21 GMT  
		Size: 46.6 MB (46645580 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fe7203031bf40ede6b42be5c3fda4ca4d75813d5bd4b1b964031a91101f44bc`  
		Last Modified: Tue, 17 Jul 2018 11:59:56 GMT  
		Size: 6.6 MB (6628142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f70fcc6b3abd37d971fff823418e9e34f70cffa0160a3baf8d7e2eea079fcf3a`  
		Last Modified: Tue, 17 Jul 2018 11:59:57 GMT  
		Size: 9.0 MB (8987743 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa2ae4496c0916db99e22c0245b34d245a7318740ae4c9f23250d636cf66291a`  
		Last Modified: Tue, 17 Jul 2018 12:52:07 GMT  
		Size: 840.2 KB (840227 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c0810e84c1a090066340c5d857bf3de97486a9c67a19884712150c85db8d04f`  
		Last Modified: Tue, 17 Jul 2018 12:52:06 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e7c233f2419ba4df692b504b8b98a4d15eb2b67544501d2212f586b784b5f5a`  
		Last Modified: Sat, 21 Jul 2018 11:14:17 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:56c3e3a087a23332cfd19541f318d3a1e24605dcbf012d111e4f0b7339c87434`  
		Last Modified: Sat, 28 Jul 2018 09:01:19 GMT  
		Size: 161.4 MB (161354549 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:11-ea-jre-sid` - linux; arm variant v7

```console
$ docker pull openjdk@sha256:bbb153446b572fe0d4dfe60661df460285177ecdfaa0afac0c1ffc8df6616a3f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **219.5 MB (219542965 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4f2b0d7a2969c53a92bfad9cfd8a82d06658b37bb30334dd476a98ed9d9e0be2`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 12:03:18 GMT
ADD file:016411fa531d65b2271f50aee3e350fc858e61add73997af4a83556197c9abd5 in / 
# Tue, 17 Jul 2018 12:03:18 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:44:22 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:44:31 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 16:11:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:11:24 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 16:11:25 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 16:11:33 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 16:11:34 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 31 Jul 2018 12:18:16 GMT
ENV JAVA_VERSION=11-ea+24
# Tue, 31 Jul 2018 12:18:17 GMT
ENV JAVA_DEBIAN_VERSION=11~24-1
# Tue, 31 Jul 2018 12:19:09 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:a4e0ee0fbc8087144c4cdef3f0495ffebba2e3ee7dfa11ff0d5a4b165ff41f7c`  
		Last Modified: Tue, 17 Jul 2018 12:15:37 GMT  
		Size: 44.5 MB (44512160 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70e3242d163ccebb1e24dafc2e4deb3b8913ee65303f56b15736a14018c6fcf6`  
		Last Modified: Tue, 17 Jul 2018 14:08:01 GMT  
		Size: 6.4 MB (6418813 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d90194ec002d2dcbfc99ba120dcf8f01ef9037e35164e5ceb9c8ceac378ec1c`  
		Last Modified: Tue, 17 Jul 2018 14:08:01 GMT  
		Size: 8.7 MB (8703423 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c9089005de6fd50a3d8cad35dc43b757155e17fa10676e63c2528f513646ff`  
		Last Modified: Tue, 17 Jul 2018 16:32:26 GMT  
		Size: 823.3 KB (823281 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7551abecfba34ecb6d5b52f240f03d79d286e26b9aed276c0e21beee6197359e`  
		Last Modified: Tue, 17 Jul 2018 16:32:26 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22132281f5baf9c78e724865205347e37288f463bef7e37f53dac4584617c720`  
		Last Modified: Tue, 17 Jul 2018 16:32:26 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6578692c9e1fae4c47385d0a8c7e04af65e7b387488a1b9706b36a040eea6c01`  
		Last Modified: Tue, 31 Jul 2018 12:36:20 GMT  
		Size: 159.1 MB (159084921 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:11-ea-jre-sid` - linux; arm64 variant v8

```console
$ docker pull openjdk@sha256:056f34027e997b3e67ed210294e65736d491e8fd46b944008334972308cf6572
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **230.3 MB (230274306 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e5a9b633870a2463d6f204e8a460f9837fd8e0f2b41005ceaadd7bb2a7f830db`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:43:33 GMT
ADD file:1145a1860bba8a4d148966c227a31ee5ee05c524c8af7a2c0963bb5671b11ad7 in / 
# Tue, 17 Jul 2018 08:43:36 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:39:52 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:40:24 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 19:56:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 19:56:32 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 19:56:37 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 19:56:40 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 19:56:41 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 28 Jul 2018 08:49:33 GMT
ENV JAVA_VERSION=11-ea+24
# Sat, 28 Jul 2018 08:49:33 GMT
ENV JAVA_DEBIAN_VERSION=11~24-1
# Sat, 28 Jul 2018 08:59:13 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:719cf01a9d639f6fad37c3abd73d6746ec6483c438952c7daf2503b9dccde689`  
		Last Modified: Tue, 17 Jul 2018 08:53:02 GMT  
		Size: 46.0 MB (45967380 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:075accf774284e7b667dd405cd13b8eeb55056113680340e3245fbd09d5d03fa`  
		Last Modified: Tue, 17 Jul 2018 15:07:59 GMT  
		Size: 6.6 MB (6647895 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a6bf6cdca1c47f36a5665bfdb0fb046730a62f0d3c944aecf285c441be0ea93`  
		Last Modified: Tue, 17 Jul 2018 15:07:59 GMT  
		Size: 9.0 MB (8981452 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36c840a5bdd30532a63df60e5079cbbe12a8fce1db657e5b27202622471ed9c7`  
		Last Modified: Tue, 17 Jul 2018 20:40:10 GMT  
		Size: 831.8 KB (831820 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f84f1479c592353313a7a93277681daa575a4af657abf7514207ccfbf82e462e`  
		Last Modified: Tue, 17 Jul 2018 20:40:10 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8029dd7284fa85df3e47a0e9b8dfcde08c81578bdf2e0421735eb084d56944ae`  
		Last Modified: Tue, 17 Jul 2018 20:40:09 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c024bdfc21f383f99e0bd27abf492f2563a5d4c19e24cd68eeec7c45b8b0649`  
		Last Modified: Sat, 28 Jul 2018 09:13:37 GMT  
		Size: 167.8 MB (167845392 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:11-ea-jre-sid` - linux; 386

```console
$ docker pull openjdk@sha256:a387089a73945a2902a72d92181cb14a1a16c9a6422ec84e933c20c7f2817fbd
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **256.5 MB (256483929 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6941f5db661f79a3941ec1244cd7099adc7371ae5993b930e7a47c07f56637b0`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 10:46:37 GMT
ADD file:9a56907f76deea3f2b22068eae8c6cc31bed7f9c7b3de38c6e99c54e77d0822e in / 
# Tue, 17 Jul 2018 10:46:41 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:30:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:31:07 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 18:10:47 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 18:10:47 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 18:10:48 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 18:10:49 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 18:10:50 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 28 Jul 2018 10:44:30 GMT
ENV JAVA_VERSION=11-ea+24
# Sat, 28 Jul 2018 10:44:31 GMT
ENV JAVA_DEBIAN_VERSION=11~24-1
# Sat, 28 Jul 2018 10:45:44 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:c4a6da94b3de8d8ecc301930050dce3da90b886c8443b00166765e0873f7abf6`  
		Last Modified: Tue, 17 Jul 2018 11:03:38 GMT  
		Size: 49.5 MB (49529462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3804bb32a028b43835bbfcaa803b7de3d0dac5cb91ca5192d83ff39548d87dc5`  
		Last Modified: Tue, 17 Jul 2018 15:11:50 GMT  
		Size: 7.2 MB (7186448 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f6b791854fa42fd340bfb473b8a46084be17fd760aec34df82fd303f96a9ca5`  
		Last Modified: Tue, 17 Jul 2018 15:11:52 GMT  
		Size: 9.5 MB (9527986 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8c7f6b57a91274b87e9359f6087b58be7100abe66a9ba7c584dafc42f56a9a3`  
		Last Modified: Tue, 17 Jul 2018 18:31:02 GMT  
		Size: 854.3 KB (854311 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3902ef34602a870d6143f6aea2221db68a6c781338755c2559f085728962d5d`  
		Last Modified: Tue, 17 Jul 2018 18:31:02 GMT  
		Size: 235.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e9504ea1c3fe592856da4c89403b65064040b103a2d264ef6cec53a9b5fc1d2`  
		Last Modified: Tue, 17 Jul 2018 18:31:02 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff782b65fcaa13c56ea4d9fbd09b4322f90f97eedb4fe09cb5d341db360dc108`  
		Last Modified: Sat, 28 Jul 2018 10:58:52 GMT  
		Size: 189.4 MB (189385356 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:11-ea-jre-sid` - linux; ppc64le

```console
$ docker pull openjdk@sha256:f41d7420c4fc7486472cf03209472e1ec2569ebcc35c5cdfd0b332de46ce8812
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **238.7 MB (238723486 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:88d51477b4afc83465754844ef14efc7a1e488a4604ab6164f704ef15f7dff03`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:18:22 GMT
ADD file:94ebec540eca8b99572e5842e1f1f2fe8cf7a62fb1366b2459edb37903e41200 in / 
# Tue, 17 Jul 2018 08:18:31 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 12:56:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:56:27 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 16:21:35 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:21:38 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 16:21:47 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 16:21:52 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 16:21:53 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 01 Aug 2018 10:40:52 GMT
ENV JAVA_VERSION=11-ea+24
# Wed, 01 Aug 2018 10:41:01 GMT
ENV JAVA_DEBIAN_VERSION=11~24-1
# Wed, 01 Aug 2018 11:08:44 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:2d7cf41bf039d34ad7c6efe6cb9dc3370c5f55c39226a13fd409d52eb991f335`  
		Last Modified: Tue, 17 Jul 2018 08:23:43 GMT  
		Size: 50.2 MB (50185044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f17647cf140d6db3c9f1f92652456b5a6bb54c33ca54b10d4dfb98f2b9f8e5c4`  
		Last Modified: Tue, 17 Jul 2018 14:13:33 GMT  
		Size: 6.9 MB (6876422 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbd26110f5fee83517301d699e51fa0068429ef004ebc1a0f923f23ededc8621`  
		Last Modified: Tue, 17 Jul 2018 14:13:33 GMT  
		Size: 9.5 MB (9494855 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39fdca2392dba04cb5aca6b662a42e69264bc5866b553b75b013e019a70b8bcd`  
		Last Modified: Tue, 17 Jul 2018 17:27:19 GMT  
		Size: 841.6 KB (841558 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d24a83bd75f6287213ae1609820714c57b8749ccdd46b8d244a7ad258cbfea9`  
		Last Modified: Tue, 17 Jul 2018 17:27:19 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:caf6c75c5753af17b26cdc2c3554b2506ea9bf9c78f92ea7357cf76341736b26`  
		Last Modified: Tue, 17 Jul 2018 17:27:19 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32daab287dae85e74cf4bb4fddd85b80bfba8fb57fc9fbc812218adf12d57d06`  
		Last Modified: Wed, 01 Aug 2018 11:36:54 GMT  
		Size: 171.3 MB (171325238 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:11-ea-jre-sid` - linux; s390x

```console
$ docker pull openjdk@sha256:43459f566e1cdf685081c9d2735dfc72989664228eaca3d8c3864d3b9bb7d436
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **207.0 MB (207017992 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b6c8e5537d1ce35b8c62ef74f0411947198425ab7a1a945b7291eb0bfb085eac`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 11:42:12 GMT
ADD file:cc7dc0768817446033aeb138e188af680cfedc409e223f9784d76e615feb4c11 in / 
# Tue, 17 Jul 2018 11:42:15 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:19:15 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:19:21 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 14:14:00 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:14:01 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 14:14:01 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 14:14:02 GMT
RUN ln -svT "/usr/lib/jvm/java-11-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 14:14:02 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 28 Jul 2018 11:53:22 GMT
ENV JAVA_VERSION=11-ea+24
# Sat, 28 Jul 2018 11:53:22 GMT
ENV JAVA_DEBIAN_VERSION=11~24-1
# Sat, 28 Jul 2018 11:53:59 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-11-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
```

-	Layers:
	-	`sha256:7ce421c266a7f090ea9857f4226f9f791cb56ece2becee63129b019e9786527d`  
		Last Modified: Tue, 17 Jul 2018 11:45:34 GMT  
		Size: 47.7 MB (47674254 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07abb9f11de8a7cf3609cab93301ed88a0a66c6f9946a1b865a2738460537a15`  
		Last Modified: Tue, 17 Jul 2018 13:29:20 GMT  
		Size: 6.8 MB (6764457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c958d9bc09e39d650d733b01f7aa4174021f01ef9e69f65e9ee399c5f4a6903f`  
		Last Modified: Tue, 17 Jul 2018 13:29:20 GMT  
		Size: 9.2 MB (9183018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36c3d7bcfef978c9842098735a554b09d072f09f794304956349268091b22914`  
		Last Modified: Tue, 17 Jul 2018 14:21:59 GMT  
		Size: 857.6 KB (857612 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3b104098d4ef083f9643039cc962c73e8510ba62946e1067bba1f35dbef2914`  
		Last Modified: Tue, 17 Jul 2018 14:21:58 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:220c30dc1f5f0eaad606ba67af9121d12c842ddb9778e474077ab8fb31852880`  
		Last Modified: Tue, 17 Jul 2018 14:21:59 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b04cd2f835f17faa23e0e67b273b6f83b3bdfd1cd7f2de050476379e1fc3851`  
		Last Modified: Sat, 28 Jul 2018 11:58:44 GMT  
		Size: 142.5 MB (142538281 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
