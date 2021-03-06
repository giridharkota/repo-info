## `debian:rc-buggy`

```console
$ docker pull debian@sha256:72148c6ab818a1a8a2bf016342b180b11f204081f510559826b13d31a867ddf2
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

### `debian:rc-buggy` - linux; amd64

```console
$ docker pull debian@sha256:859d76d807e202354d9e3920b3cff78388c214ff036e854420dfe44f1ac12802
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **48.7 MB (48725811 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:50192e6b7d1df73274bfa98b73c36bbec5fa379ffadd313b3dbaa91fbacca3d1`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 00:24:39 GMT
ADD file:f04b64a73c29541d70cda855be7033dbd8e0b173ab11cd93458f3400fd270d85 in / 
# Tue, 17 Jul 2018 00:24:40 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 00:31:55 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:e367ac4072dc48836ab52faeb39e943b075e21aa02c1a88f838651b9b384de50`  
		Last Modified: Tue, 17 Jul 2018 00:39:42 GMT  
		Size: 48.7 MB (48725588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b211b70c94849b14e5b9436debb9951bde674c421be598deb88472d687f8a8b1`  
		Last Modified: Tue, 17 Jul 2018 00:50:31 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; arm variant v5

```console
$ docker pull debian@sha256:f0d25019b2e77be5aab9c026c7eea05ddfdb3960c68b8547f39c528eeee8283e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **46.6 MB (46645804 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5f0c926d256f3173aa2445dce76eba6d96f008dd17a37a89c15fdcd1771a54ef`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:53:54 GMT
ADD file:feed6b12801621af72a787e98590f6fd783022a609efc8254532712521e6c570 in / 
# Tue, 17 Jul 2018 08:53:55 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 09:01:04 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:b6112397569f950be7cab355fd3cb9fb3b089c080499c1eebc269ecb7cc3715c`  
		Last Modified: Tue, 17 Jul 2018 09:06:21 GMT  
		Size: 46.6 MB (46645580 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a87507a5b86ac3fb19ef4e0a98b10eafc23eccb105c996f60caf88e9bce84088`  
		Last Modified: Tue, 17 Jul 2018 09:12:48 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; arm variant v7

```console
$ docker pull debian@sha256:6e0fbb01c423fc75fd9186a255c9dfcab91a272050963c557f0d2020e2229473
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **44.5 MB (44512386 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f2406af5cde8df7804855b159d293cce88bdf8dfceaad278c91c56c05a0d32b0`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 12:03:18 GMT
ADD file:016411fa531d65b2271f50aee3e350fc858e61add73997af4a83556197c9abd5 in / 
# Tue, 17 Jul 2018 12:03:18 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 12:09:23 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:a4e0ee0fbc8087144c4cdef3f0495ffebba2e3ee7dfa11ff0d5a4b165ff41f7c`  
		Last Modified: Tue, 17 Jul 2018 12:15:37 GMT  
		Size: 44.5 MB (44512160 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62380714a6fe3a2a99019f28327efc39a97ee450766bffe95d3bfbb9d5f9383b`  
		Last Modified: Tue, 17 Jul 2018 12:22:37 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; arm64 variant v8

```console
$ docker pull debian@sha256:179ee114598e982e48c4c8050d6ac9092c3542d8925a70bf7d126fed5988c7b1
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **46.0 MB (45967606 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a7d027c97936b3087cbe12ffabccbaa1e124a823e0c994274c2c86fc67bfa46b`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:43:33 GMT
ADD file:1145a1860bba8a4d148966c227a31ee5ee05c524c8af7a2c0963bb5671b11ad7 in / 
# Tue, 17 Jul 2018 08:43:36 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 08:51:12 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:719cf01a9d639f6fad37c3abd73d6746ec6483c438952c7daf2503b9dccde689`  
		Last Modified: Tue, 17 Jul 2018 08:53:02 GMT  
		Size: 46.0 MB (45967380 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:151ec2ac9d3d6ee805fbe968ac8612e0a785f66f815647c7c89df8e3fe18a94a`  
		Last Modified: Tue, 17 Jul 2018 09:01:18 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; 386

```console
$ docker pull debian@sha256:d3d5bccb9a6683b978d68456fa746082f1a5e2c1a691851d344ef2f3e9f7c2fe
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **49.5 MB (49529688 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2bcc842d6e31724e9c9874e70a45b727cf7a86211c452695b5e0d8afe08146d1`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 10:46:37 GMT
ADD file:9a56907f76deea3f2b22068eae8c6cc31bed7f9c7b3de38c6e99c54e77d0822e in / 
# Tue, 17 Jul 2018 10:46:41 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 10:54:06 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:c4a6da94b3de8d8ecc301930050dce3da90b886c8443b00166765e0873f7abf6`  
		Last Modified: Tue, 17 Jul 2018 11:03:38 GMT  
		Size: 49.5 MB (49529462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0597f6517d3950b8fc886288955577457d7a59c4417fc90809478ec84d035109`  
		Last Modified: Tue, 17 Jul 2018 11:15:17 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; ppc64le

```console
$ docker pull debian@sha256:a34733e8aad0ea1d4d007caae640f777affa0012547a84edc21f57c9dace4c47
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **50.2 MB (50185269 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8958b2111efbc0a8ea5defdd7ee4deb8f74f94291fe81acbc4af8a346fdadec5`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 08:18:22 GMT
ADD file:94ebec540eca8b99572e5842e1f1f2fe8cf7a62fb1366b2459edb37903e41200 in / 
# Tue, 17 Jul 2018 08:18:31 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 08:22:13 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:2d7cf41bf039d34ad7c6efe6cb9dc3370c5f55c39226a13fd409d52eb991f335`  
		Last Modified: Tue, 17 Jul 2018 08:23:43 GMT  
		Size: 50.2 MB (50185044 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e29edbde9398f83f3a7b49692685280efe815c277a9bd19b23d9448b2b2a9a55`  
		Last Modified: Tue, 17 Jul 2018 08:28:55 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `debian:rc-buggy` - linux; s390x

```console
$ docker pull debian@sha256:4cfeeedaf893613c132b9aa566fffed5ccce56076a3496393573e008ff3ae4db
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **47.7 MB (47674479 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ad91c15838f6fd84e13c607af96d1e88538317bac2e81ba03a18b6b22cb6076`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 17 Jul 2018 11:42:12 GMT
ADD file:cc7dc0768817446033aeb138e188af680cfedc409e223f9784d76e615feb4c11 in / 
# Tue, 17 Jul 2018 11:42:15 GMT
CMD ["bash"]
# Tue, 17 Jul 2018 11:44:41 GMT
RUN echo 'deb http://deb.debian.org/debian rc-buggy main' > /etc/apt/sources.list.d/experimental.list
```

-	Layers:
	-	`sha256:7ce421c266a7f090ea9857f4226f9f791cb56ece2becee63129b019e9786527d`  
		Last Modified: Tue, 17 Jul 2018 11:45:34 GMT  
		Size: 47.7 MB (47674254 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ebdcc95f0af7a7faef29541c8faf0b1b89f53d9e8d77aaf642e5b08d31bd1a7`  
		Last Modified: Tue, 17 Jul 2018 11:48:29 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
