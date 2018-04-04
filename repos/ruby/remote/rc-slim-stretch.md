## `ruby:rc-slim-stretch`

```console
$ docker pull ruby@sha256:14917f4752cd5b47170c554c847ddd456100d57730f2a693a1f9c39047e4b551
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

### `ruby:rc-slim-stretch` - linux; amd64

```console
$ docker pull ruby@sha256:e8316e0f736647668a9e36f669a9790bfdafc05973e50a6f4045a3bf4b5e65aa
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **78.1 MB (78112926 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5cdee26bbbc87e7b6efc566b5f1f0c4c15624bdc549574edb98d8eb977d19332`
-	Default Command: `["irb"]`

```dockerfile
# Tue, 13 Mar 2018 22:26:49 GMT
ADD file:b380df301ccb5ca09f0d7cd5697ed402fa55f3e9bc5df2f4d489ba31f28de58a in / 
# Tue, 13 Mar 2018 22:26:49 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 19:35:58 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 19:35:58 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 31 Mar 2018 08:27:25 GMT
ENV RUBY_MAJOR=2.6-rc
# Sat, 31 Mar 2018 08:27:26 GMT
ENV RUBY_VERSION=2.6.0-preview1
# Sat, 31 Mar 2018 08:27:26 GMT
ENV RUBY_DOWNLOAD_SHA256=1d99139116e4e245ce543edb137b2a8873c26e9f0bde88d8cee6789617cc8d0e
# Sat, 31 Mar 2018 08:27:26 GMT
ENV RUBYGEMS_VERSION=2.7.6
# Sat, 31 Mar 2018 08:27:26 GMT
ENV BUNDLER_VERSION=1.16.1
# Sat, 31 Mar 2018 08:29:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Sat, 31 Mar 2018 08:29:52 GMT
ENV GEM_HOME=/usr/local/bundle
# Sat, 31 Mar 2018 08:29:53 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Sat, 31 Mar 2018 08:29:53 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 31 Mar 2018 08:29:54 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Sat, 31 Mar 2018 08:29:54 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:c73ab1c6897bf5c11da3c95cab103e7ca8cf10a6d041eda2ff836f45a40e3d3b`  
		Last Modified: Tue, 13 Mar 2018 22:52:31 GMT  
		Size: 45.1 MB (45135077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fae2064f516668e46adaf61367e025df9d91cdf38f7de5a6716fabdb9d9b558a`  
		Last Modified: Wed, 14 Mar 2018 20:51:34 GMT  
		Size: 12.8 MB (12811933 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b95fc1a710b703ef4b3a2b15eec3b82415bf210df49559f5785f912ac0d44d3`  
		Last Modified: Wed, 14 Mar 2018 20:51:29 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b6942acbd7a57b89a974e15198a844f629e319752ad90fd41e97b639229df5f`  
		Last Modified: Sat, 31 Mar 2018 09:20:37 GMT  
		Size: 20.2 MB (20165547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a46bad0b40913c68797c6f94e433b4a43c32c53679356f4fa9fc21bda5ef0ee6`  
		Last Modified: Sat, 31 Mar 2018 09:20:31 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-slim-stretch` - linux; arm variant v5

```console
$ docker pull ruby@sha256:f85b9f1992f01f3f39ecfaa23615ccdb8100647379384853f5bd035ae853d575
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **74.9 MB (74929023 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:abcb98d710170efcc4aa569ea2108bae1ac8cc6c53292b21dac8331e0d6250d6`
-	Default Command: `["irb"]`

```dockerfile
# Wed, 14 Mar 2018 20:01:02 GMT
ADD file:df0457084f7e40c64d40dd7ffb2d5365160faee6f8b02c443bc3d1cb36a0f40d in / 
# Wed, 14 Mar 2018 20:01:03 GMT
CMD ["bash"]
# Wed, 28 Mar 2018 01:24:11 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 28 Mar 2018 01:24:12 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Mon, 02 Apr 2018 16:38:56 GMT
ENV RUBY_MAJOR=2.6-rc
# Mon, 02 Apr 2018 16:38:57 GMT
ENV RUBY_VERSION=2.6.0-preview1
# Mon, 02 Apr 2018 16:38:57 GMT
ENV RUBY_DOWNLOAD_SHA256=1d99139116e4e245ce543edb137b2a8873c26e9f0bde88d8cee6789617cc8d0e
# Mon, 02 Apr 2018 16:38:58 GMT
ENV RUBYGEMS_VERSION=2.7.6
# Mon, 02 Apr 2018 16:38:58 GMT
ENV BUNDLER_VERSION=1.16.1
# Mon, 02 Apr 2018 16:41:57 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Mon, 02 Apr 2018 16:41:58 GMT
ENV GEM_HOME=/usr/local/bundle
# Mon, 02 Apr 2018 16:41:59 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Mon, 02 Apr 2018 16:41:59 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 02 Apr 2018 16:42:00 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Mon, 02 Apr 2018 16:42:00 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:25301cba2d4ef04878f7296fe55faa4b0b2fafbc29758d9fca5a199350d7827c`  
		Last Modified: Wed, 14 Mar 2018 20:12:18 GMT  
		Size: 43.8 MB (43819573 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae120bec15ea201e26e8ffa24439d9a59d8290d99ed4484705d41960d2522a67`  
		Last Modified: Wed, 28 Mar 2018 02:09:12 GMT  
		Size: 11.4 MB (11377108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f89d8a10ec684b6c7a1d6121ae77782c0e1a183d8ddbdf28507e8654ffcd966`  
		Last Modified: Wed, 28 Mar 2018 02:09:08 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3fbd39bfead44b0eafd315fceeddde4161bf2487f67df4f9c15268881a21fa2f`  
		Last Modified: Mon, 02 Apr 2018 17:39:49 GMT  
		Size: 19.7 MB (19731941 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7d9f3166ee018c18f8ebcf5c379ced3862f723f55afb041e7028585b00d32b4`  
		Last Modified: Mon, 02 Apr 2018 17:39:45 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-slim-stretch` - linux; arm variant v7

```console
$ docker pull ruby@sha256:3fe853035651f457283d6572a5e043e49732f350140f66f3d470f8a616f8a5ce
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **72.3 MB (72290633 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2b4e2e8070f4b2266494c24ab1fbcec311fec2c7b1568f73264cadf5e3583b78`
-	Default Command: `["irb"]`

```dockerfile
# Wed, 14 Mar 2018 12:32:32 GMT
ADD file:a48681cb8186079633f55084b5ecf518e0c50f24cfb6eb56bd42bca88f26e28d in / 
# Wed, 14 Mar 2018 12:32:33 GMT
CMD ["bash"]
# Thu, 29 Mar 2018 02:28:11 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Thu, 29 Mar 2018 02:28:12 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Mon, 02 Apr 2018 16:34:02 GMT
ENV RUBY_MAJOR=2.6-rc
# Mon, 02 Apr 2018 16:34:02 GMT
ENV RUBY_VERSION=2.6.0-preview1
# Mon, 02 Apr 2018 16:34:03 GMT
ENV RUBY_DOWNLOAD_SHA256=1d99139116e4e245ce543edb137b2a8873c26e9f0bde88d8cee6789617cc8d0e
# Mon, 02 Apr 2018 16:34:06 GMT
ENV RUBYGEMS_VERSION=2.7.6
# Mon, 02 Apr 2018 16:34:07 GMT
ENV BUNDLER_VERSION=1.16.1
# Mon, 02 Apr 2018 16:36:40 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Mon, 02 Apr 2018 16:36:41 GMT
ENV GEM_HOME=/usr/local/bundle
# Mon, 02 Apr 2018 16:36:42 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Mon, 02 Apr 2018 16:36:42 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 02 Apr 2018 16:36:44 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Mon, 02 Apr 2018 16:36:44 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:1296b637c2f207ccc536f8e55bad6857ee417d3b5ea4c82a92a8e8621a970f50`  
		Last Modified: Wed, 14 Mar 2018 12:44:05 GMT  
		Size: 41.9 MB (41857435 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89ab4cd3c2e91cdf5456246e416f642b102ba89dd3a8bcd105fa27dceb16c273`  
		Last Modified: Thu, 29 Mar 2018 02:52:33 GMT  
		Size: 10.9 MB (10897965 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:856f7558c32413645d05926936c19b6d4b0a924af4a68d959d08ccfb08ccdc22`  
		Last Modified: Thu, 29 Mar 2018 02:52:29 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcb140542e1fe10ae6e8e2de99139352fa8ef3fcf83377d2b47edea296094c43`  
		Last Modified: Mon, 02 Apr 2018 17:30:00 GMT  
		Size: 19.5 MB (19534832 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34d83c5f91af64469ea1d606c0a0113c8e9b1c83e7d1ddbe4b9a51a958d9d225`  
		Last Modified: Mon, 02 Apr 2018 17:29:55 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-slim-stretch` - linux; arm64 variant v8

```console
$ docker pull ruby@sha256:f05075d84ec4185e5be40f57baa7bc729fbb925c4a43eada39305456aa3b74ae
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **74.5 MB (74463701 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b6cde4bbb1975d807590cf4b095969dfa9ae9177422d3a25759f351b458fd416`
-	Default Command: `["irb"]`

```dockerfile
# Wed, 14 Mar 2018 17:30:57 GMT
ADD file:2ebfda145008a73d7d0f2dc29946bfc3ad65048b3a3f0ca0283263e413b692d4 in / 
# Wed, 14 Mar 2018 17:30:58 GMT
CMD ["bash"]
# Thu, 15 Mar 2018 01:46:25 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 01:46:26 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Mon, 02 Apr 2018 17:08:22 GMT
ENV RUBY_MAJOR=2.6-rc
# Mon, 02 Apr 2018 17:08:23 GMT
ENV RUBY_VERSION=2.6.0-preview1
# Mon, 02 Apr 2018 17:08:24 GMT
ENV RUBY_DOWNLOAD_SHA256=1d99139116e4e245ce543edb137b2a8873c26e9f0bde88d8cee6789617cc8d0e
# Mon, 02 Apr 2018 17:08:25 GMT
ENV RUBYGEMS_VERSION=2.7.6
# Mon, 02 Apr 2018 17:08:26 GMT
ENV BUNDLER_VERSION=1.16.1
# Mon, 02 Apr 2018 17:17:38 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Mon, 02 Apr 2018 17:17:39 GMT
ENV GEM_HOME=/usr/local/bundle
# Mon, 02 Apr 2018 17:17:41 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Mon, 02 Apr 2018 17:17:43 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 02 Apr 2018 17:17:47 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Mon, 02 Apr 2018 17:17:48 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:3476b6ec1aa77d47beaf22adc259097130bcc9eec853636fb1dcf4f5c2925a56`  
		Last Modified: Wed, 14 Mar 2018 17:45:20 GMT  
		Size: 42.9 MB (42907825 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88415cebbee5b9f473eccb6f89c082fe36573424f76e3afbe12e3de368ebb613`  
		Last Modified: Thu, 15 Mar 2018 03:07:46 GMT  
		Size: 11.6 MB (11622486 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4ef7b7f97ee9b7cfc08e7dcce407b68ecd188be8b0fa730c745122152b18d17`  
		Last Modified: Thu, 15 Mar 2018 03:07:41 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:816b712520c4d9e1321c84857af2a9419055a60ffb9433a4e4daed10697657f8`  
		Last Modified: Mon, 02 Apr 2018 19:29:02 GMT  
		Size: 19.9 MB (19933020 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b92cc19c84a279a5fab54ffc05600799144a93287e0e4da30eacdb1d2ea9f1e0`  
		Last Modified: Mon, 02 Apr 2018 19:28:19 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-slim-stretch` - linux; 386

```console
$ docker pull ruby@sha256:01551cd48d5d89a04c888005c14b0dd98d827cfc52faf0e74e9fccad033eb51a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **81.8 MB (81842423 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1ac44920f8919d9b174d0a69c2daa49b67440a5ae8a3d9a6e7c49bd2a6b441c4`
-	Default Command: `["irb"]`

```dockerfile
# Tue, 27 Mar 2018 15:59:32 GMT
ADD file:3a8e11cd900f3ac48c7d30158b5a85e65d78680861eb910888c20ef4ae42756f in / 
# Tue, 27 Mar 2018 15:59:33 GMT
CMD ["bash"]
# Wed, 28 Mar 2018 18:42:10 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 28 Mar 2018 18:42:11 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 01 Apr 2018 07:15:46 GMT
ENV RUBY_MAJOR=2.6-rc
# Sun, 01 Apr 2018 07:15:46 GMT
ENV RUBY_VERSION=2.6.0-preview1
# Sun, 01 Apr 2018 07:15:47 GMT
ENV RUBY_DOWNLOAD_SHA256=1d99139116e4e245ce543edb137b2a8873c26e9f0bde88d8cee6789617cc8d0e
# Sun, 01 Apr 2018 07:15:47 GMT
ENV RUBYGEMS_VERSION=2.7.6
# Sun, 01 Apr 2018 07:15:47 GMT
ENV BUNDLER_VERSION=1.16.1
# Sun, 01 Apr 2018 07:18:26 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Sun, 01 Apr 2018 07:18:26 GMT
ENV GEM_HOME=/usr/local/bundle
# Sun, 01 Apr 2018 07:18:27 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Sun, 01 Apr 2018 07:18:27 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sun, 01 Apr 2018 07:18:28 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Sun, 01 Apr 2018 07:18:28 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:bebcce41445a0be67e63665c298f73217c532640d75de97624d019429de2dd93`  
		Last Modified: Thu, 15 Mar 2018 01:29:27 GMT  
		Size: 45.8 MB (45843420 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7616121b44917be88e11160106ba0f7aa0fedcac7e2eed65073c03e209326dc1`  
		Last Modified: Sun, 01 Apr 2018 11:40:35 GMT  
		Size: 16.3 MB (16251618 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e93a5e87608d0b607ce235ddd514df956e05add18856a2a90fa57898daaeeab`  
		Last Modified: Sun, 01 Apr 2018 11:40:27 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b3aac3ad876b739ef72f9427cb6ec06d52f06fd6665fe060dd3c2df725bff75`  
		Last Modified: Sun, 01 Apr 2018 11:40:32 GMT  
		Size: 19.7 MB (19747016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9fc1298806b579491594bc5ae25f794d450f83770d78429bdc20fbab20150e1`  
		Last Modified: Sun, 01 Apr 2018 11:40:27 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-slim-stretch` - linux; ppc64le

```console
$ docker pull ruby@sha256:b775e6cdfcccc3e102bc117e7a2bd6598dbffb3a13b07e49e5bf388544360734
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **78.0 MB (77996324 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:46735ad916dfef56c2afda563e9629f0730b5d4082cf1d73fd346a1a8bddbff4`
-	Default Command: `["irb"]`

```dockerfile
# Wed, 14 Mar 2018 00:34:58 GMT
ADD file:cd28b9ad859ce13c0d4fee241178bba68cc8f696eb1722a67ac3c62c2c64e087 in / 
# Wed, 14 Mar 2018 00:34:59 GMT
CMD ["bash"]
# Thu, 15 Mar 2018 04:40:08 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 04:40:15 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Mon, 02 Apr 2018 17:01:11 GMT
ENV RUBY_MAJOR=2.6-rc
# Mon, 02 Apr 2018 17:01:13 GMT
ENV RUBY_VERSION=2.6.0-preview1
# Mon, 02 Apr 2018 17:01:15 GMT
ENV RUBY_DOWNLOAD_SHA256=1d99139116e4e245ce543edb137b2a8873c26e9f0bde88d8cee6789617cc8d0e
# Mon, 02 Apr 2018 17:01:18 GMT
ENV RUBYGEMS_VERSION=2.7.6
# Mon, 02 Apr 2018 17:01:20 GMT
ENV BUNDLER_VERSION=1.16.1
# Mon, 02 Apr 2018 17:12:23 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Mon, 02 Apr 2018 17:12:27 GMT
ENV GEM_HOME=/usr/local/bundle
# Mon, 02 Apr 2018 17:12:30 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Mon, 02 Apr 2018 17:12:33 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 02 Apr 2018 17:12:38 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Mon, 02 Apr 2018 17:12:40 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:1743854d776e01d7f49a30bb37dbbfb45e788dc99753cb027de750d2da47a89c`  
		Last Modified: Wed, 14 Mar 2018 00:42:50 GMT  
		Size: 45.4 MB (45377043 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d61d4e65f786e6636412978f1d4bad6bae2ba9a9e2b3d12816a803b693b3f8d9`  
		Last Modified: Thu, 15 Mar 2018 06:34:07 GMT  
		Size: 12.2 MB (12206905 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:593224a2050b28bf8b910c3bd38d13b7fd79a63df166f6d9bec1b3bba1695d40`  
		Last Modified: Thu, 15 Mar 2018 06:33:55 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e78cb6541650646256a98fdf9c23e00d944271866d52a4960830432698e44c75`  
		Last Modified: Mon, 02 Apr 2018 19:05:14 GMT  
		Size: 20.4 MB (20411974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d994f93fc90050b63948ac1820e230823ace68f57bb1b4a18f4d92cf76a4694b`  
		Last Modified: Mon, 02 Apr 2018 19:05:10 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `ruby:rc-slim-stretch` - linux; s390x

```console
$ docker pull ruby@sha256:b505ace82339a546efcebf8f8cd8d3da96cc8a0e41cc6a224ebdf587352d000a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **78.8 MB (78751411 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8787b6c068e8ef155bf811ca63d59a2bf5b8e356e7025591be63be2bd7523a26`
-	Default Command: `["irb"]`

```dockerfile
# Wed, 14 Mar 2018 05:23:49 GMT
ADD file:0d1edaf8dfadb3f8f127a53726a33b0679e90f8d66b891fa1434e47535999cc2 in / 
# Wed, 14 Mar 2018 05:23:50 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 07:40:42 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 07:40:43 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Mon, 02 Apr 2018 16:58:42 GMT
ENV RUBY_MAJOR=2.6-rc
# Mon, 02 Apr 2018 16:58:42 GMT
ENV RUBY_VERSION=2.6.0-preview1
# Mon, 02 Apr 2018 16:58:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d99139116e4e245ce543edb137b2a8873c26e9f0bde88d8cee6789617cc8d0e
# Mon, 02 Apr 2018 16:58:42 GMT
ENV RUBYGEMS_VERSION=2.7.6
# Mon, 02 Apr 2018 16:58:43 GMT
ENV BUNDLER_VERSION=1.16.1
# Mon, 02 Apr 2018 17:01:59 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Mon, 02 Apr 2018 17:01:59 GMT
ENV GEM_HOME=/usr/local/bundle
# Mon, 02 Apr 2018 17:01:59 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Mon, 02 Apr 2018 17:01:59 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 02 Apr 2018 17:02:00 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Mon, 02 Apr 2018 17:02:00 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:4777ebf2c92e16819bdac8f1861addbd58c0ed81dbb208e677f5bc404331f1df`  
		Last Modified: Wed, 14 Mar 2018 05:28:34 GMT  
		Size: 45.0 MB (44977147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:608f1ad4a10a31ee4d0b55b3a8a7a3ae88cd8d4fcee3a750c8a80c76a8615f72`  
		Last Modified: Wed, 14 Mar 2018 08:16:16 GMT  
		Size: 13.2 MB (13214258 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df37eb51932f998667b3c36ce433566862b954e8a7d93dc833429f4c98ec2454`  
		Last Modified: Wed, 14 Mar 2018 08:16:13 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c0611fc1bc2d17d7c9973d401309e04ea87e0c570c3842dcc860be75e8c6f487`  
		Last Modified: Mon, 02 Apr 2018 17:56:29 GMT  
		Size: 20.6 MB (20559635 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36a40e73cc938cf29aad7b3a37ecc5a244269ff4cf4cdd2c636adc6bb378a5a4`  
		Last Modified: Mon, 02 Apr 2018 17:56:28 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip