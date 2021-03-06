## `maven:3-jdk-7`

```console
$ docker pull maven@sha256:7f71f87721036b98d791c270a527c384b6c934585623fded908707df6c5864fa
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

### `maven:3-jdk-7` - linux; amd64

```console
$ docker pull maven@sha256:65711a3191b669faedecbfceb210c5b35fabd65586aafb5140339a56afef965d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **222.7 MB (222712762 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:84a20ec9fab92fb7dcf2f50cefccf24ebf06224122727c6b2e1d780b9df11631`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 00:20:47 GMT
ADD file:b90e572f7462a23e2e4eda57269941ee7d8f078ca8ab1eefca86927713e13365 in / 
# Tue, 17 Jul 2018 00:20:48 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 03:04:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 03:04:59 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 03:06:27 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:21:31 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:21:31 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:21:32 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:21:33 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:21:33 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 17 Jul 2018 06:21:33 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 06:21:34 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 06:22:53 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 17:01:38 GMT
ARG MAVEN_VERSION=3.5.4
# Tue, 17 Jul 2018 17:01:39 GMT
ARG USER_HOME_DIR=/root
# Tue, 17 Jul 2018 17:01:39 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Tue, 17 Jul 2018 17:01:39 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Tue, 17 Jul 2018 17:01:43 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 17 Jul 2018 17:01:55 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 17 Jul 2018 17:01:56 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 17 Jul 2018 17:01:56 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 17 Jul 2018 17:01:57 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 17 Jul 2018 17:01:57 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 17 Jul 2018 17:01:57 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:d660b1f15b9bfb8142f50b518156f2d364d9642fe05854538b060498e2f7928d`  
		Last Modified: Tue, 17 Jul 2018 00:34:02 GMT  
		Size: 54.3 MB (54252125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46dde23c37b3419122bb597461c1a48bdea1842aaae7dbe728dfa20a9aabe11b`  
		Last Modified: Tue, 17 Jul 2018 03:47:37 GMT  
		Size: 17.5 MB (17538077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ebaeb0745895220f609d4aa703e4563c39de239a2d00b85bece23a3ca3ac735`  
		Last Modified: Tue, 17 Jul 2018 03:48:27 GMT  
		Size: 43.3 MB (43297880 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba483765e5a5940bdbe52f7a5b5e591842365f723606f5121ba1f900b42efa13`  
		Last Modified: Tue, 17 Jul 2018 07:10:16 GMT  
		Size: 828.2 KB (828239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a2fdf2277bd55505d828f7765ec2f4e8f24183129636afeaa5b3389d7008ae99`  
		Last Modified: Tue, 17 Jul 2018 07:10:16 GMT  
		Size: 246.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a778f99270e0adcb63e2696dcc5cda72de4c88878d0765c9d5232fc1aeece07e`  
		Last Modified: Tue, 17 Jul 2018 07:10:16 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0884f4286e6c07cd530102e34f90e200e8a496296e8b11453cc1af93432b4dfb`  
		Last Modified: Tue, 17 Jul 2018 07:10:38 GMT  
		Size: 97.8 MB (97805729 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a08c41d9acbbadd64321433bc6151d4f1fbb0096324100da52cf444ffbba4084`  
		Last Modified: Tue, 17 Jul 2018 17:11:31 GMT  
		Size: 9.0 MB (8989222 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b597cedfddb1b2d420564c4fc824b21f790779a013c2d08489ca5e8a3515336c`  
		Last Modified: Tue, 17 Jul 2018 17:11:29 GMT  
		Size: 751.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:963ea10a630aa6e39e041b71e099f7b3a786bd7862d4cae1ccbc82c2e700ac77`  
		Last Modified: Tue, 17 Jul 2018 17:11:29 GMT  
		Size: 363.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-7` - linux; arm variant v5

```console
$ docker pull maven@sha256:03a3e3b4bfe3f61daeb521ba84961a00c5bccdb708995b6b2cb4e93dde86ebe0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **205.4 MB (205370502 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d10f8e6d949c97a5c3c2c2fbdd0861a73ecbf56fab4f18e2c4873e013ab69f51`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 08:50:04 GMT
ADD file:4f71ce5a537d5b850f449dc85c4ab5092c673eb0784e112eaeed004c1053c959 in / 
# Tue, 17 Jul 2018 08:50:05 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:41:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 11:41:34 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 11:42:50 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:44:47 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:44:47 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 12:44:48 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 12:44:49 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:44:50 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 17 Jul 2018 12:44:50 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 12:44:50 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 12:46:25 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 14:53:28 GMT
ARG MAVEN_VERSION=3.5.4
# Tue, 17 Jul 2018 14:53:28 GMT
ARG USER_HOME_DIR=/root
# Tue, 17 Jul 2018 14:53:29 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Tue, 17 Jul 2018 14:53:30 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Tue, 17 Jul 2018 14:53:36 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 17 Jul 2018 14:53:36 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 17 Jul 2018 14:53:36 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 17 Jul 2018 14:53:37 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 17 Jul 2018 14:53:38 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 17 Jul 2018 14:53:38 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 17 Jul 2018 14:53:39 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:6517acaf0fe60ef69bfcf8dfa76c43b4a1e5b4fedea418026ded2b0fe506ac2b`  
		Last Modified: Tue, 17 Jul 2018 09:02:44 GMT  
		Size: 52.4 MB (52447839 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:951a82006f9a5d9219f349459f2e0e765002a1f68a81eefc081835abb73adc94`  
		Last Modified: Tue, 17 Jul 2018 11:58:23 GMT  
		Size: 17.0 MB (17028700 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:513930d4e92a4d1fb2e4d30fdb76c665bbb11a38b998bc375ed378c99501ab43`  
		Last Modified: Tue, 17 Jul 2018 11:58:58 GMT  
		Size: 41.1 MB (41142226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f9e0f9683d5f759a3dccc913cb6f5653c83221b85e47ee7d1a915f5ca8d106a`  
		Last Modified: Tue, 17 Jul 2018 12:57:35 GMT  
		Size: 821.5 KB (821454 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0df4691bc9198b01266c74c00afe823faf0c66a8aa3527ef153b843ec5a48213`  
		Last Modified: Tue, 17 Jul 2018 12:57:33 GMT  
		Size: 246.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76827465ff79862f272a8206185854e6c4522eef8a233ab41db1328fe7a97510`  
		Last Modified: Tue, 17 Jul 2018 12:57:33 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6c7b19331d4a0c8386b72ef4827bb9e29cb2ed5dbe770f970cc1c9c72a91faf`  
		Last Modified: Tue, 17 Jul 2018 12:57:50 GMT  
		Size: 84.9 MB (84939560 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92e0f2fd85b567255e878b807aa2a6fd1f2f87fe358c55310892251cbeb52bcf`  
		Last Modified: Tue, 17 Jul 2018 14:57:30 GMT  
		Size: 9.0 MB (8989238 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e218cb714488c99b66885063c4e48b97c1f226f5670cfa2267609f3c0fe76154`  
		Last Modified: Tue, 17 Jul 2018 14:57:29 GMT  
		Size: 749.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6c1f656352ddf39f0b8bd718d50eb5c58a5d9d64d15e862c182e3c43d7df655`  
		Last Modified: Tue, 17 Jul 2018 14:57:30 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-7` - linux; arm variant v7

```console
$ docker pull maven@sha256:6224af756609aef8961992e8a748fc9df61b6010415c845be0255cd81e370409
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **200.0 MB (200042492 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b8d69477fe4c5724e67996326296ac364f72cfda9abb04a4c10fb12500dd5c76`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 11:59:28 GMT
ADD file:b6521e3d1f270115e5b6c8df3fb62b87aae252b99045c6884f1c071d88fecf10 in / 
# Tue, 17 Jul 2018 11:59:35 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 13:40:40 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 13:40:42 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 13:41:46 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:25:31 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 16:25:31 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 16:25:32 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 16:25:33 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 16:25:34 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 17 Jul 2018 16:25:34 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 16:25:35 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 16:27:02 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 17:03:33 GMT
ARG MAVEN_VERSION=3.5.4
# Tue, 17 Jul 2018 17:03:33 GMT
ARG USER_HOME_DIR=/root
# Tue, 17 Jul 2018 17:03:34 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Tue, 17 Jul 2018 17:03:34 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Tue, 17 Jul 2018 17:03:38 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 17 Jul 2018 17:03:38 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 17 Jul 2018 17:03:39 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 17 Jul 2018 17:03:39 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 17 Jul 2018 17:03:40 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 17 Jul 2018 17:03:40 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 17 Jul 2018 17:03:40 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:fbd7fa58000c551825cee932912ff0e71b08d10d3a21e72fa231f872c5ec3109`  
		Last Modified: Tue, 17 Jul 2018 12:10:53 GMT  
		Size: 50.2 MB (50187773 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8d9a9aa87bb2d7aaaef5230826591f3a257cdde7443239673f8a87f99ee7ffa`  
		Last Modified: Tue, 17 Jul 2018 14:06:05 GMT  
		Size: 16.7 MB (16712260 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f12745f5f1fe2c0c7e66de9818fd2e49a955fd18db2ccd7f512bbefacbbd8d3b`  
		Last Modified: Tue, 17 Jul 2018 14:06:43 GMT  
		Size: 39.8 MB (39763909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2065bba238a150fbf3c4b8474b84041df61432c5cc213c33713e057e351e4397`  
		Last Modified: Tue, 17 Jul 2018 16:39:44 GMT  
		Size: 795.4 KB (795352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0da4675c364e430667e76eabdf643c6fbe0a35e8ab1a4fc5832d2a84d8c408e9`  
		Last Modified: Tue, 17 Jul 2018 16:39:44 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:682aa544eb6a60a6075cc15e52213598d20dedbde879a3453cc1b3c744a15077`  
		Last Modified: Tue, 17 Jul 2018 16:39:44 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e917a48921d9f4699139d4ef19ed1bb01d6c9fe2c677b04d1c65e1570cccc9a`  
		Last Modified: Tue, 17 Jul 2018 16:39:59 GMT  
		Size: 83.6 MB (83592471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:408daca834b3153b306ba2c6b1ece275bd1f2744f4764e42ae9f85e1515ca0c1`  
		Last Modified: Tue, 17 Jul 2018 17:08:08 GMT  
		Size: 9.0 MB (8989240 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e34d767b373cd95a9be2d6d15261c98c05ece93a3a61dd4665cc594e162b4fb1`  
		Last Modified: Tue, 17 Jul 2018 17:08:09 GMT  
		Size: 750.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2584b3d52ec27cf13df8b04ce5269a33da0c7cc8ec116399239609b9ec1889a7`  
		Last Modified: Tue, 17 Jul 2018 17:08:07 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-7` - linux; arm64 variant v8

```console
$ docker pull maven@sha256:14828bd9c79e4192bd0d9cd0b74054338a14cc5fdff281fadf6c65c33a46f5ef
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **206.0 MB (206038853 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7f5094308cd6440e71bfd17e4bf87a1172fbb547f7404d226c6b098a62d917cf`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:16:46 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:16:48 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:18:27 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:30:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:30:52 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:30:56 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:30:59 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:31:00 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Jun 2018 09:14:33 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 09:14:33 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 09:21:40 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 23 Jun 2018 08:44:04 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 23 Jun 2018 08:44:05 GMT
ARG USER_HOME_DIR=/root
# Sat, 23 Jun 2018 08:44:05 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 23 Jun 2018 08:44:06 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 23 Jun 2018 08:44:14 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 23 Jun 2018 08:44:15 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 23 Jun 2018 08:44:16 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 23 Jun 2018 08:44:17 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 23 Jun 2018 08:44:17 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 23 Jun 2018 08:44:18 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 23 Jun 2018 08:44:19 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bc4956efcaf7d30060a373d34961e3c6e71ee0317cb5381a180230a397c5442`  
		Last Modified: Sat, 05 May 2018 09:43:52 GMT  
		Size: 17.2 MB (17213842 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71a9e408db2031cacf4541c01e9c992c2cdfd06fd26ad42c508faa3b0a71aae4`  
		Last Modified: Sat, 05 May 2018 09:44:04 GMT  
		Size: 41.0 MB (41017251 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f0aef3aa00d6f5d9a0a4fd9a9df66b7ae66fb7dbf3e05a0f94cc4e77fbd4e4d8`  
		Last Modified: Sat, 05 May 2018 13:10:11 GMT  
		Size: 823.5 KB (823452 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d393ba719b098e0559f24a57503eeafdf70771d57a7f4ba2516543a72f7d989`  
		Last Modified: Sat, 05 May 2018 13:10:09 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0576deba4b8555fe094940d78f65f3bd55827e47963729a6252cdc79a4a7aa9`  
		Last Modified: Sat, 05 May 2018 13:10:09 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0509ee2655e1c66859e0b429d53c79f7578238c98832a3df5c074cc7c78bba6d`  
		Last Modified: Tue, 12 Jun 2018 09:46:22 GMT  
		Size: 86.5 MB (86546734 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d12524832158988b3ecc37034eb09514f06769abbe2386c99945b1ffca233f6e`  
		Last Modified: Sat, 23 Jun 2018 08:51:24 GMT  
		Size: 9.0 MB (8989228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef5963a7f91f3de8e9635f951027f6ecd7064fe8cc351b226c2c89f5fb4df7ab`  
		Last Modified: Sat, 23 Jun 2018 08:51:22 GMT  
		Size: 752.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff8c000953ad1bd8a99a6aa968a7ae68641562d640612edd612d35b258e34618`  
		Last Modified: Sat, 23 Jun 2018 08:51:22 GMT  
		Size: 362.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-7` - linux; 386

```console
$ docker pull maven@sha256:2ae2bb7f691a0e58ef90c14919763039e9025ac7d37b2147e76faae7ff5bfbb7
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **235.6 MB (235622127 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4fa4d06122b61054b62f477c15def4f18eb2c3700a8919bbc4ccd7c185349dce`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Tue, 17 Jul 2018 10:41:14 GMT
ADD file:edf13e4ea5255fbdbe91ff11bf281f8dc1ed1790ea095ab1ff341f0abc03f58c in / 
# Tue, 17 Jul 2018 10:41:14 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 14:25:21 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 14:25:26 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 17 Jul 2018 14:27:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 18:19:46 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 18:19:47 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 18:19:48 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 18:19:48 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 18:19:49 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 17 Jul 2018 18:19:49 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 18:19:49 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 18:21:32 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 19:04:03 GMT
ARG MAVEN_VERSION=3.5.4
# Tue, 17 Jul 2018 19:04:03 GMT
ARG USER_HOME_DIR=/root
# Tue, 17 Jul 2018 19:04:04 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Tue, 17 Jul 2018 19:04:04 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Tue, 17 Jul 2018 19:04:08 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 17 Jul 2018 19:04:08 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 17 Jul 2018 19:04:09 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 17 Jul 2018 19:04:20 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 17 Jul 2018 19:04:21 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 17 Jul 2018 19:04:21 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 17 Jul 2018 19:04:21 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:357075fdb6ed4cabaab3293713922024245238f5596815e10a36b24c0a498f08`  
		Last Modified: Tue, 17 Jul 2018 10:56:53 GMT  
		Size: 54.5 MB (54483269 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61274d86633cfcbd74890e3b94b540ad3cdbcb6a769aa68579f642fd13a32eb1`  
		Last Modified: Tue, 17 Jul 2018 15:08:53 GMT  
		Size: 19.8 MB (19832967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:501abb8e70591a1130105f440ab6d42bf38283ba8d4078896dde609700fdc926`  
		Last Modified: Tue, 17 Jul 2018 15:09:43 GMT  
		Size: 43.9 MB (43946227 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbd7d3a7fde4bedc376cfd040cacc16522fef3c6bb2de05c699aaff08c8a45b1`  
		Last Modified: Tue, 17 Jul 2018 18:52:36 GMT  
		Size: 831.2 KB (831227 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b42e3f5b5b15c6fb390c5281e4e9db8e38dc2690adf412d29b4a476b158c3b04`  
		Last Modified: Tue, 17 Jul 2018 18:52:35 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19b992a14ff16e701e8114edf8930479346b8c7d3cb56e29df04cf5eebc0c023`  
		Last Modified: Tue, 17 Jul 2018 18:52:36 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ba9185d748505f5b1e48eab95bc8b334dbe8faa49224203ed07827c4f98ad15`  
		Last Modified: Tue, 17 Jul 2018 18:53:06 GMT  
		Size: 107.5 MB (107537737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d76b8cc21759dc2747395e41604a205cfd266c662e995f17aaba6e44fa68f507`  
		Last Modified: Tue, 17 Jul 2018 19:12:33 GMT  
		Size: 9.0 MB (8989214 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef3ab635ff7a68a751384cfcfa113cd6e0c18c72c723dc4f628430dd58cbebab`  
		Last Modified: Tue, 17 Jul 2018 19:12:27 GMT  
		Size: 749.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe6134e99376dcc2497aa94715d7f1064fe4e5257ad26019ef3b0949c086e8da`  
		Last Modified: Tue, 17 Jul 2018 19:12:27 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-7` - linux; ppc64le

```console
$ docker pull maven@sha256:ab693b0e440bb361fc080ff7301a39e08ed7ee572a94b0568664b6b717aa7c85
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **211.2 MB (211172689 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:81a790d6ce5e6b478139332bf6d6cb8dc47698a2969b7a49f81f4ecb20e4291d`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 05 May 2018 08:58:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 08:58:32 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:02:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 14:45:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 14:45:35 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 14:45:37 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 14:45:38 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 14:45:39 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Jun 2018 08:44:14 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 08:44:17 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 08:48:16 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 23 Jun 2018 08:21:59 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 23 Jun 2018 08:22:00 GMT
ARG USER_HOME_DIR=/root
# Sat, 23 Jun 2018 08:22:01 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 23 Jun 2018 08:22:02 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 23 Jun 2018 08:22:07 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 23 Jun 2018 08:22:08 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 23 Jun 2018 08:22:09 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 23 Jun 2018 08:22:09 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 23 Jun 2018 08:22:10 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 23 Jun 2018 08:22:11 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 23 Jun 2018 08:22:12 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4330bc6a5e0bcfbe95c4a5b5982f6866f41b6cdc2d95042061dac233ebb605c`  
		Last Modified: Sat, 05 May 2018 10:53:05 GMT  
		Size: 17.6 MB (17586999 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6b80419adae67f8e9f1a9fee9a620fdcbdff5713ef2d259c091aaca6ae14914`  
		Last Modified: Sat, 05 May 2018 10:53:52 GMT  
		Size: 42.8 MB (42759764 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67f70ff6ff6c5b1a5ea4fc0a6061e960596b9ac2cdb288ccb8ac1b8ef9d77bc3`  
		Last Modified: Sat, 05 May 2018 15:18:51 GMT  
		Size: 824.0 KB (824035 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:278742896236d7b4da4ee75ff4516dd95d023f210ea3a5b2ec7eb5dddcd85b81`  
		Last Modified: Sat, 05 May 2018 15:18:50 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:194c9f92e61a0cd8e159b89318830d32498cd5f37cd3f06bbe09fa20261b6e66`  
		Last Modified: Sat, 05 May 2018 15:18:50 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f465bc4a857df3ae52cce951671aeea82d3106c9ff14b53bebbca4958dc9d2db`  
		Last Modified: Tue, 12 Jun 2018 09:12:54 GMT  
		Size: 87.6 MB (87618354 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47205f311e0f369037b3c12e7808c1b95afaf164a0a28983880f00054eeaf568`  
		Last Modified: Sat, 23 Jun 2018 08:30:04 GMT  
		Size: 9.0 MB (8989232 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1086ea2ade611b5cca56036d6c4449ef93cee62fc409c2a9c9076d48774f4ce5`  
		Last Modified: Sat, 23 Jun 2018 08:30:02 GMT  
		Size: 753.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6003127b5f5d2878609e7470e13ef0846883084a6fa230771236e148ba9db468`  
		Last Modified: Sat, 23 Jun 2018 08:30:02 GMT  
		Size: 362.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-7` - linux; s390x

```console
$ docker pull maven@sha256:e3542d9f9d9084236f9fa08f31d12cb1505f4e87d9ed2dea5aab7e7fb140c2a8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **212.6 MB (212596421 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2570d2553d8fe4de788ead59d7e2b049d975259f5af99d7c346f7fda0dad6e67`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:30:55 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:30:56 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:31:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:18:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:18:25 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:18:25 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 13:18:26 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 13:18:26 GMT
ENV JAVA_HOME=/docker-java-home
# Tue, 12 Jun 2018 11:54:07 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 11:54:07 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 11:54:49 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 23 Jun 2018 11:43:31 GMT
ARG MAVEN_VERSION=3.5.4
# Sat, 23 Jun 2018 11:43:32 GMT
ARG USER_HOME_DIR=/root
# Sat, 23 Jun 2018 11:43:33 GMT
ARG SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d
# Sat, 23 Jun 2018 11:43:33 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries
# Sat, 23 Jun 2018 11:43:38 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.4/binaries MAVEN_VERSION=3.5.4 SHA=ce50b1c91364cb77efe3776f756a6d92b76d9038b0a0782f7d53acf1e997a14d USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Sat, 23 Jun 2018 11:43:39 GMT
ENV MAVEN_HOME=/usr/share/maven
# Sat, 23 Jun 2018 11:43:39 GMT
ENV MAVEN_CONFIG=/root/.m2
# Sat, 23 Jun 2018 11:43:39 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Sat, 23 Jun 2018 11:43:39 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Sat, 23 Jun 2018 11:43:39 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Sat, 23 Jun 2018 11:43:40 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37be7fda6df150d239266145f4a84caa9f37d32c535a19acbb408973995140fd`  
		Last Modified: Sat, 05 May 2018 12:45:40 GMT  
		Size: 17.8 MB (17787031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7861d9ab6f9ef13ede92760c03359fa98b5718a37494c7ae5f428bad6ab514d`  
		Last Modified: Sat, 05 May 2018 12:46:05 GMT  
		Size: 43.4 MB (43389402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90db59706ece89097dac868a91f2b61c65997c86cfcc25200e4a74d9ce9eae58`  
		Last Modified: Sat, 05 May 2018 13:33:17 GMT  
		Size: 837.7 KB (837678 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5ba4c1f95a2186b0f608dd3d0a86d2fe33e6c60d12cc50bc85367488aedb165`  
		Last Modified: Sat, 05 May 2018 13:33:16 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87ca61f47dddf3ad3f00acb5022e5e5d12ceadd7023167461d91e07bb02aa5f0`  
		Last Modified: Sat, 05 May 2018 13:33:17 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:27ed01c3914edf31ce2522223dffd1de17cecab3039d394fe374664da79c2054`  
		Last Modified: Tue, 12 Jun 2018 12:01:23 GMT  
		Size: 87.1 MB (87125745 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b7fdaf815d60525aef9ece0430571d385476610e8e49d709e5c066a02db528e1`  
		Last Modified: Sat, 23 Jun 2018 11:46:51 GMT  
		Size: 9.0 MB (8989214 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0dbb12395fb4a7b85ff2830c9826a864ffaeb78cf5aec2aeb4b1623bd909bbe8`  
		Last Modified: Sat, 23 Jun 2018 11:46:49 GMT  
		Size: 751.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8595e12c6b177ccec1c1257f5fa22293938d93e025d136752a65810ab0a1ba1e`  
		Last Modified: Sat, 23 Jun 2018 11:46:50 GMT  
		Size: 364.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
