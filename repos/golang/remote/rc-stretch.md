## `golang:rc-stretch`

```console
$ docker pull golang@sha256:7e920b32c3368bdb4c8862d12662de60c5c846932eb4b54a2f139a44a84dacc0
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `golang:rc-stretch` - linux; amd64

```console
$ docker pull golang@sha256:3e90d12c0512b7daecc3bde25dfa2311fb90e8b1929085af8463978cbeee07c7
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **337.4 MB (337375888 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:50f1aa64fd70186d8e976f5134659b04b7bc184bfe425f8396f5195621a0cf9c`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 26 Jun 2018 21:24:58 GMT
ADD file:f21d7c14104d5d9fa99f271177e765a3472f5a69398bb78f34f7401e9b2df837 in / 
# Tue, 26 Jun 2018 21:24:58 GMT
CMD ["bash"]
# Tue, 26 Jun 2018 22:16:40 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 26 Jun 2018 22:16:48 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 26 Jun 2018 22:17:29 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 27 Jun 2018 22:20:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Wed, 27 Jun 2018 22:20:11 GMT
ENV GOLANG_VERSION=1.11beta1
# Wed, 27 Jun 2018 22:20:29 GMT
RUN set -eux; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) goRelArch='linux-amd64'; goRelSha256='df7fe096ffab5d331d35c6d038d2ec0426b45ce17f55a93037e371d3af9d4e6d' ;; 		armhf) goRelArch='linux-armv6l'; goRelSha256='844ed9e34b118a9c2b069a18924a7879236929e08c887a92e5be1af5d701fb90' ;; 		arm64) goRelArch='linux-arm64'; goRelSha256='9c1795148e777c81ac3cb381e3ea970eea60f5db2323658c061e5c4382125dd4' ;; 		i386) goRelArch='linux-386'; goRelSha256='a6e804652f58785b3dfe272d96b8206250210e7ba7bdcb1ffb726ab3753db4af' ;; 		ppc64el) goRelArch='linux-ppc64le'; goRelSha256='66529a525c0369d2b79ecd19f6d16444ed162c9bf88f7b37715520841c36de65' ;; 		s390x) goRelArch='linux-s390x'; goRelSha256='731b9e6ac0d4c9709297f0efc1a6455589b978d2ecc207184d3e5be07a130c9c' ;; 		*) goRelArch='src'; goRelSha256='5955eeb8f45e02aa5357fc18e62f1fe6c1b19e0c50aba93b8b9d9ef13b862dda'; 			echo >&2; echo >&2 "warning: current architecture ($dpkgArch) does not have a corresponding Go binary release; will be building from source"; echo >&2 ;; 	esac; 		url="https://golang.org/dl/go${GOLANG_VERSION}.${goRelArch}.tar.gz"; 	wget -O go.tgz "$url"; 	echo "${goRelSha256} *go.tgz" | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		if [ "$goRelArch" = 'src' ]; then 		echo >&2; 		echo >&2 'error: UNIMPLEMENTED'; 		echo >&2 'TODO install golang-any from jessie-backports for GOROOT_BOOTSTRAP (and uninstall after build)'; 		echo >&2; 		exit 1; 	fi; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Wed, 27 Jun 2018 22:20:30 GMT
ENV GOPATH=/go
# Wed, 27 Jun 2018 22:20:30 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 27 Jun 2018 22:20:31 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Wed, 27 Jun 2018 22:20:31 GMT
WORKDIR /go
```

-	Layers:
	-	`sha256:0bd44ff9c2cf1129ef8cea689b3e10e6498f64d2f8d5532caae55841b474bf3a`  
		Last Modified: Tue, 26 Jun 2018 21:36:36 GMT  
		Size: 45.3 MB (45319224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:047670ddbd2a37cb7940be99332555b0a9f4f2531802e50c06128c340ccd0c0d`  
		Last Modified: Tue, 26 Jun 2018 22:30:05 GMT  
		Size: 10.8 MB (10774053 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea7d5dc8943870545f4eecc6b06b3fd6b12b987dc99f0bbcfee8f132044fc9e2`  
		Last Modified: Tue, 26 Jun 2018 22:30:03 GMT  
		Size: 4.3 MB (4336270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae7ad5906a7580677bdf8a8d57749814520c2c6a2054604c115ba6e8646363aa`  
		Last Modified: Tue, 26 Jun 2018 22:30:55 GMT  
		Size: 50.1 MB (50062264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15f6351ddb3796295061478a28f09752a99b61fdb5160e0456b687f3dd52e04a`  
		Last Modified: Wed, 27 Jun 2018 22:29:30 GMT  
		Size: 57.6 MB (57565582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7d930c1545f5f8dd60d33f27b95cc6f26f9f30759d37264ef84a1f9081014e7`  
		Last Modified: Wed, 27 Jun 2018 22:29:50 GMT  
		Size: 169.3 MB (169318369 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e30fc2f13a0a23db1d40bbddb264db6de62b51920c5f6aeaa143a34e144ac00`  
		Last Modified: Wed, 27 Jun 2018 22:29:09 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip