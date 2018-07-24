## `couchbase:enterprise-5.5.0`

```console
$ docker pull couchbase@sha256:050509300b4cf1433af82e243ece2419476addf4a805b459779f975a75fc369b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `couchbase:enterprise-5.5.0` - linux; amd64

```console
$ docker pull couchbase@sha256:d310da5e9660b3d593c0a30ec188ea3f8fefae08520a1997d4a0b0079a6f7721
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **321.4 MB (321381646 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0ebf0208bf14f30e3483e5dc75a45a726509ddad4f3daf6dab42d2b583c5d0b4`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["couchbase-server"]`

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
# Tue, 17 Jul 2018 10:51:27 GMT
MAINTAINER Couchbase Docker Team <docker@couchbase.com>
# Tue, 17 Jul 2018 10:51:58 GMT
RUN apt-get update &&     apt-get install -yq runit wget python-httplib2 chrpath tzdata     lsof lshw sysstat net-tools numactl  &&     apt-get autoremove && apt-get clean &&     rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
# Mon, 23 Jul 2018 21:19:54 GMT
ARG CB_VERSION=5.5.0
# Mon, 23 Jul 2018 21:19:54 GMT
ARG CB_RELEASE_URL=https://packages.couchbase.com/releases
# Mon, 23 Jul 2018 21:19:54 GMT
ARG CB_PACKAGE=couchbase-server-enterprise_5.5.0-ubuntu16.04_amd64.deb
# Mon, 23 Jul 2018 21:19:54 GMT
ARG CB_SHA256=9eb499e953451e0675d4a3d04cee40b654d3d548d54f1fdece97c2a192f7d778
# Mon, 23 Jul 2018 21:19:55 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/couchbase/bin:/opt/couchbase/bin/tools:/opt/couchbase/bin/install
# Mon, 23 Jul 2018 21:19:56 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_5.5.0-ubuntu16.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=9eb499e953451e0675d4a3d04cee40b654d3d548d54f1fdece97c2a192f7d778 CB_VERSION=5.5.0
RUN groupadd -g 1000 couchbase && useradd couchbase -u 1000 -g couchbase -M
# Mon, 23 Jul 2018 21:20:39 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_5.5.0-ubuntu16.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=9eb499e953451e0675d4a3d04cee40b654d3d548d54f1fdece97c2a192f7d778 CB_VERSION=5.5.0
RUN export INSTALL_DONT_START_SERVER=1 &&     wget -N $CB_RELEASE_URL/$CB_VERSION/$CB_PACKAGE &&     echo "$CB_SHA256  $CB_PACKAGE" | sha256sum -c - &&     dpkg -i ./$CB_PACKAGE && rm -f ./$CB_PACKAGE
# Mon, 23 Jul 2018 21:20:40 GMT
COPY file:9a90647aed4e88ee15c7efe9abbafbf7a89c3174cbe85d6b5492cde1aa9c6355 in /etc/service/couchbase-server/run 
# Mon, 23 Jul 2018 21:20:41 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_5.5.0-ubuntu16.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=9eb499e953451e0675d4a3d04cee40b654d3d548d54f1fdece97c2a192f7d778 CB_VERSION=5.5.0
RUN chown -R couchbase:couchbase /etc/service
# Mon, 23 Jul 2018 21:20:42 GMT
COPY file:8196fd8e201c5fc3873a0faa3cec28b0d85633e363c0c5788434f5b9a81cfa5b in /usr/local/bin/ 
# Mon, 23 Jul 2018 21:20:42 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_5.5.0-ubuntu16.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=9eb499e953451e0675d4a3d04cee40b654d3d548d54f1fdece97c2a192f7d778 CB_VERSION=5.5.0
RUN ln -s dummy.sh /usr/local/bin/iptables-save &&     ln -s dummy.sh /usr/local/bin/lvdisplay &&     ln -s dummy.sh /usr/local/bin/vgdisplay &&     ln -s dummy.sh /usr/local/bin/pvdisplay
# Mon, 23 Jul 2018 21:20:43 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_5.5.0-ubuntu16.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=9eb499e953451e0675d4a3d04cee40b654d3d548d54f1fdece97c2a192f7d778 CB_VERSION=5.5.0
RUN chrpath -r '$ORIGIN/../lib' /opt/couchbase/bin/curl
# Mon, 23 Jul 2018 21:20:44 GMT
COPY file:5d67fa23771c82cbce2e1a74900e7c0ce4d1466a002273f57ab13d52d6b844b3 in / 
# Mon, 23 Jul 2018 21:20:44 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Mon, 23 Jul 2018 21:20:44 GMT
CMD ["couchbase-server"]
# Mon, 23 Jul 2018 21:20:45 GMT
EXPOSE 11207/tcp 11210/tcp 11211/tcp 18091/tcp 18092/tcp 18093/tcp 18094/tcp 18095/tcp 18096/tcp 8091/tcp 8092/tcp 8093/tcp 8094/tcp 8095/tcp 8096/tcp
# Mon, 23 Jul 2018 21:20:45 GMT
VOLUME [/opt/couchbase/var]
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
	-	`sha256:346308c1dac0600f1976818a633e464ac7f0968a0ab8ffb1b322f3fd0de12981`  
		Last Modified: Tue, 17 Jul 2018 10:58:30 GMT  
		Size: 14.3 MB (14295079 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69553a0ca5c6af1866bcbfa490f036c2c32aad11f9995999d05f8742ebad98c2`  
		Last Modified: Mon, 23 Jul 2018 21:22:04 GMT  
		Size: 2.1 KB (2078 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f402ec2c7775b91c313d725248f43e40fa962bc1f696853bad2283ccf385f21c`  
		Last Modified: Mon, 23 Jul 2018 21:22:50 GMT  
		Size: 263.8 MB (263782352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9c433a8fc500c7d16f3434891770996c1f9fb3353d3c73d0d78b8c053292174`  
		Last Modified: Mon, 23 Jul 2018 21:22:04 GMT  
		Size: 400.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d04bd60521ce71d054ba490efce8da959205a85152e505f1892a84f4b829ecda`  
		Last Modified: Mon, 23 Jul 2018 21:22:01 GMT  
		Size: 407.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:064c889941d7386e787ba40dcaa2aeeffa8b8168430059e032433e69440f5ba4`  
		Last Modified: Mon, 23 Jul 2018 21:22:01 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3093f1240545ddaa1de02d6854f25212342bb61a7ef48a78b31faecc30329a13`  
		Last Modified: Mon, 23 Jul 2018 21:22:01 GMT  
		Size: 218.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bc543be32d3b9093e437fa8b0f3304afaeb58421567f7dabcad5039068e1003`  
		Last Modified: Mon, 23 Jul 2018 21:22:03 GMT  
		Size: 107.5 KB (107454 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:575700e8e9a2b97bfd5736e3441c60726a048c39e7cc40376e43e41cc14aa854`  
		Last Modified: Mon, 23 Jul 2018 21:22:01 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip