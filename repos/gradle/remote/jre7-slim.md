## `gradle:jre7-slim`

```console
$ docker pull gradle@sha256:fe1cf3e7951d754326203ceb4a456aa514de8973d5c56280ded75ee4a438965d
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; 386

### `gradle:jre7-slim` - linux; amd64

```console
$ docker pull gradle@sha256:70d7995ca727b92fec427bd63528a1591e4711f789ff4c054a7398da2dad543e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **180.9 MB (180895019 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:77b9d890d67e1898724dff05b1e40e43b805d55359bf66dbdc005c633175c86c`
-	Default Command: `["gradle"]`

```dockerfile
# Tue, 17 Jul 2018 00:21:41 GMT
ADD file:f41225557de4ad90c9325b91551c90e0262532b9270ea997ddf92d688387649e in / 
# Tue, 17 Jul 2018 00:21:42 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 06:23:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 06:23:46 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 06:23:47 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 06:23:47 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 06:27:25 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 17 Jul 2018 06:27:25 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 06:27:26 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 06:28:22 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 16:29:32 GMT
CMD ["gradle"]
# Tue, 17 Jul 2018 16:29:32 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 17 Jul 2018 23:23:25 GMT
ENV GRADLE_VERSION=4.9
# Tue, 17 Jul 2018 23:23:56 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 23:23:56 GMT
ARG GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
# Tue, 17 Jul 2018 23:24:02 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 17 Jul 2018 23:24:11 GMT
USER [gradle]
# Tue, 17 Jul 2018 23:24:11 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 17 Jul 2018 23:24:12 GMT
WORKDIR /home/gradle
# Tue, 17 Jul 2018 23:24:15 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:5bba3ecb4cd6374a19da45f2a3db0a9c0804984358b3bb4b666c28944016e5ff`  
		Last Modified: Tue, 17 Jul 2018 00:35:30 GMT  
		Size: 30.1 MB (30120164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:83aaae4a41047243bc7114b57d6abbf93493ca7760a12f1bcb11f7796e792a3f`  
		Last Modified: Tue, 17 Jul 2018 07:14:08 GMT  
		Size: 463.7 KB (463742 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:77071b36c9a8bf79837590aee3dcf02df92603573b10a2f99b154d05a80ed68b`  
		Last Modified: Tue, 17 Jul 2018 07:14:08 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:44de20d9dd075cf58bc5c1696f04dd15b9aa035f0f8a86eda6ded43da087c3d1`  
		Last Modified: Tue, 17 Jul 2018 07:14:08 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb8892ada1858955ed00ab8408454978d93feab29003ea2c3e437e005c724cdc`  
		Last Modified: Tue, 17 Jul 2018 07:20:04 GMT  
		Size: 61.6 MB (61627351 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f65751921f3c0ebcc457dfe5fb0047b1b4b3d389ab0beae61af7dfb794f1d9e2`  
		Last Modified: Tue, 17 Jul 2018 23:39:52 GMT  
		Size: 12.4 MB (12360158 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ecc5ac985402d01fc769bd3f7f770e888c2fce100a297598b4dc21b1a2c538`  
		Last Modified: Tue, 17 Jul 2018 23:39:58 GMT  
		Size: 76.3 MB (76323087 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78cd385570beabbd7eb975e0da4b17a85a6b0f8a07c36dc55e44e67c35685968`  
		Last Modified: Tue, 17 Jul 2018 23:39:49 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7-slim` - linux; arm variant v5

```console
$ docker pull gradle@sha256:a76f1486f145aa2a21f9badc1bb7ce7b680440ab9a74376a3cdb06d9cc4be07a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.8 MB (168805281 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dd31b2db7a7507b3c0a484cadcaa101e11a5fe93f553cfc2f4acca7d5c0c48b2`
-	Default Command: `["gradle"]`

```dockerfile
# Tue, 17 Jul 2018 08:50:57 GMT
ADD file:e303ac4cacd7ac2a0a69960e76235ca4a7305f8db9cfae9f97c5dafe0cb57c9c in / 
# Tue, 17 Jul 2018 08:50:59 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 09:21:21 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 09:21:22 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 09:21:22 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 09:21:23 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 09:23:19 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 17 Jul 2018 09:23:19 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 09:23:19 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 09:24:08 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 13:10:16 GMT
CMD ["gradle"]
# Tue, 17 Jul 2018 13:10:16 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 18 Jul 2018 08:50:24 GMT
ENV GRADLE_VERSION=4.9
# Wed, 18 Jul 2018 08:50:51 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Wed, 18 Jul 2018 08:50:52 GMT
ARG GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
# Wed, 18 Jul 2018 08:50:58 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 18 Jul 2018 08:50:59 GMT
USER [gradle]
# Wed, 18 Jul 2018 08:50:59 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 18 Jul 2018 08:50:59 GMT
WORKDIR /home/gradle
# Wed, 18 Jul 2018 08:51:03 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:669d043a9b2bd51eea9e767c0315e0ad02bd9f56f1ef5f6172fa53d78285ac5a`  
		Last Modified: Tue, 17 Jul 2018 09:03:26 GMT  
		Size: 28.4 MB (28430654 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32c284edd78c5a0cec0dabc2d10500872e2acfb829d77dd47be7bc8901de22b7`  
		Last Modified: Tue, 17 Jul 2018 09:34:38 GMT  
		Size: 456.5 KB (456467 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ffb7a4e02c9453c20bf5f6c4b61f86382c39d0cc51055486accedc5bd8e136d2`  
		Last Modified: Tue, 17 Jul 2018 09:34:37 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b322e91969e8bed0ecb1c9ed5354b0e1c1c150f2fa66e6bc978dc26b66b1bdab`  
		Last Modified: Tue, 17 Jul 2018 09:34:37 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb1aecbe4486983d55775e55c8abfe1dda93b09522fd74149e03f4cbab9a6624`  
		Last Modified: Tue, 17 Jul 2018 09:36:35 GMT  
		Size: 51.4 MB (51429294 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05487797061589a7dd344c9464e4acd5c3cd7d14edcd657240a684e0351f3917`  
		Last Modified: Wed, 18 Jul 2018 08:57:30 GMT  
		Size: 12.2 MB (12165286 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55c517e7ca38a59cd1122322b36d1c4f63c9d2825d6a29e37dc8d25ef10928cd`  
		Last Modified: Wed, 18 Jul 2018 08:57:36 GMT  
		Size: 76.3 MB (76322967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47303b4b2e3c02a8571cddcddffdd199ae9de34b7c6fa354bfcca3fcc205b617`  
		Last Modified: Wed, 18 Jul 2018 08:57:27 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7-slim` - linux; arm variant v7

```console
$ docker pull gradle@sha256:34fb0b7bc3fc967d28e33761ad75b699dc08d7352b21204822966a8fdf648990
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **165.4 MB (165363833 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e94ce176437fa5aa80e0db438493587d835e00ca098f96a6c1722032977a8158`
-	Default Command: `["gradle"]`

```dockerfile
# Tue, 17 Jul 2018 12:00:33 GMT
ADD file:32d146255a9263416cb50a32e6079a40852e3ae1db6b0e30134cde4d24917309 in / 
# Tue, 17 Jul 2018 12:00:36 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 12:49:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 12:49:25 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 12:49:26 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 12:49:27 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 12:51:22 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 17 Jul 2018 12:51:22 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 12:51:23 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 12:52:14 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 16:47:30 GMT
CMD ["gradle"]
# Tue, 17 Jul 2018 16:47:30 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 18 Jul 2018 12:00:37 GMT
ENV GRADLE_VERSION=4.9
# Wed, 18 Jul 2018 12:01:09 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Wed, 18 Jul 2018 12:01:09 GMT
ARG GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
# Wed, 18 Jul 2018 12:01:17 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 18 Jul 2018 12:01:17 GMT
USER [gradle]
# Wed, 18 Jul 2018 12:01:18 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 18 Jul 2018 12:01:18 GMT
WORKDIR /home/gradle
# Wed, 18 Jul 2018 12:01:21 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:093a70fc20ffe401f4cf25ac9cf7d08c8d511df67aba90ee8c4eec4f8cb2c67e`  
		Last Modified: Tue, 17 Jul 2018 12:12:07 GMT  
		Size: 26.3 MB (26286960 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b078f4f7755c20eeb56b303c14bc884b2d44e3e654c17e3bff0cb23722f88b4c`  
		Last Modified: Tue, 17 Jul 2018 13:03:55 GMT  
		Size: 432.3 KB (432315 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b3c65fa31d20562a41d9fc300fedb1915412f1ab5dc29fa5317c356e879c6cb`  
		Last Modified: Tue, 17 Jul 2018 13:03:55 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f892c36d0a5a971da85854b94cb5ed3fb69996bb9c4ae0ca69995aefe2cd452d`  
		Last Modified: Tue, 17 Jul 2018 13:03:55 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7ed0567529edb8f57c81ed22e121560af74e8c1e0e81111b04fb21f752001b9`  
		Last Modified: Tue, 17 Jul 2018 13:05:20 GMT  
		Size: 50.3 MB (50299640 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff2e553e54fead7fdafb8e880f9f3775f0495e03d96d7d88f9234d63507b7514`  
		Last Modified: Wed, 18 Jul 2018 12:09:25 GMT  
		Size: 12.0 MB (12021299 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:639f3af66215d2ee69c459b8bd33f5fec388b0ef33518b585b1027bd95d3b5df`  
		Last Modified: Wed, 18 Jul 2018 12:09:58 GMT  
		Size: 76.3 MB (76323007 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1237a19c10b920427322c4e02cd358dd2d17a6dd898a05f65843151edc1ae93a`  
		Last Modified: Wed, 18 Jul 2018 12:09:22 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7-slim` - linux; 386

```console
$ docker pull gradle@sha256:75477170539ec884a59c4fb4d5b1179aaec4a645bdffdc2b567f9e0e67243ab8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **192.8 MB (192769029 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:118853121da2892bd027a4198cd91f2eca5df606d96ddee22732dda1f5d0427b`
-	Default Command: `["gradle"]`

```dockerfile
# Tue, 17 Jul 2018 10:42:32 GMT
ADD file:9f28594bd37e3d6105c4b8e438188e5f1c270ba5fa552b2b4969a43a0a84730d in / 
# Tue, 17 Jul 2018 10:42:35 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:30:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jul 2018 11:30:59 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jul 2018 11:31:01 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jul 2018 11:31:02 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 17 Jul 2018 11:33:19 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 17 Jul 2018 11:33:19 GMT
ENV JAVA_VERSION=7u181
# Tue, 17 Jul 2018 11:33:19 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 17 Jul 2018 11:34:49 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 17 Jul 2018 19:20:25 GMT
CMD ["gradle"]
# Tue, 17 Jul 2018 19:20:25 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 18 Jul 2018 00:48:11 GMT
ENV GRADLE_VERSION=4.9
# Wed, 18 Jul 2018 00:49:05 GMT
RUN apt-get update && 	apt-get install -y --no-install-recommends 		unzip 		wget && 	rm -rf /var/lib/apt/lists/*
# Wed, 18 Jul 2018 00:49:12 GMT
ARG GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
# Wed, 18 Jul 2018 00:49:19 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 18 Jul 2018 00:49:30 GMT
USER [gradle]
# Wed, 18 Jul 2018 00:49:30 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 18 Jul 2018 00:49:30 GMT
WORKDIR /home/gradle
# Wed, 18 Jul 2018 00:49:33 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=e66e69dce8173dd2004b39ba93586a184628bc6c28461bc771d6835f7f9b0d28
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:08ccc2995d065af2cd0d4ce4d10d2409e68dcfd7b947820dea2d5371344277e3`  
		Last Modified: Tue, 17 Jul 2018 10:58:32 GMT  
		Size: 30.3 MB (30270010 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d27765bec26e1d6c46befeb564ef6ee5f2122d7a68fa415dbd856cb9a7c6df4a`  
		Last Modified: Tue, 17 Jul 2018 12:04:09 GMT  
		Size: 466.3 KB (466284 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48f4434c09ccf5267ea7a53104b29f03ec003ab6f5fc1efac068dcc8be6abe11`  
		Last Modified: Tue, 17 Jul 2018 12:04:09 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d716a5df985be1ad2420509b15a3773caf63ec7c569984010094855099c2943`  
		Last Modified: Tue, 17 Jul 2018 12:04:09 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e613cb5a1dc2982676d4e6137f76b02c0c2765cb0ee8ad2ee48ddb1654d39e7a`  
		Last Modified: Tue, 17 Jul 2018 12:07:20 GMT  
		Size: 73.2 MB (73214466 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a39e26944fa1c66ded770992c6c84f87105a5ba944877e2b7b90c88372cd092`  
		Last Modified: Wed, 18 Jul 2018 01:06:08 GMT  
		Size: 12.5 MB (12494672 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5cee95088742839a4e85f4476096d9fea582ac59d4e0edf1b77af61ef8749863`  
		Last Modified: Wed, 18 Jul 2018 01:06:20 GMT  
		Size: 76.3 MB (76323080 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eefe792d585be7811d694425975dc500d1cc68888d8a254b36ca71a9e3ea5755`  
		Last Modified: Wed, 18 Jul 2018 01:06:03 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
