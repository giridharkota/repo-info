## `traefik:maroilles-nanoserver`

```console
$ docker pull traefik@sha256:5cd1da0e5e0cb681c463bd998b9c77900d07f202055fbc60d31b7b4edc075fc9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2363; amd64

### `traefik:maroilles-nanoserver` - windows version 10.0.14393.2363; amd64

```console
$ docker pull traefik@sha256:b72ae6693aaaf25729ea34d138f7cdbcfaf3c248e3b126904c886839a898f061
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **435.6 MB (435563808 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:423bec8ba219fbbe84ceffda9c55036f35abee299620a221ba7e3512b97f6155`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Tue, 10 Jul 2018 21:16:01 GMT
RUN Install update 10.0.14393.2363
# Thu, 02 Aug 2018 21:03:40 GMT
RUN cmd /S /C #(nop) COPY file:4c94379aa4d378c3412fd0a5ac3edfef56d6836d9638f135e43481fdbadf297c in \traefik.exe 
# Thu, 02 Aug 2018 21:03:43 GMT
RUN cmd /S /C #(nop)  VOLUME [C:/etc/traefik]
# Thu, 02 Aug 2018 21:03:44 GMT
RUN cmd /S /C #(nop)  VOLUME [C:/etc/ssl]
# Thu, 02 Aug 2018 21:03:45 GMT
RUN cmd /S /C #(nop)  EXPOSE 80/tcp
# Thu, 02 Aug 2018 21:03:46 GMT
RUN cmd /S /C #(nop)  ENTRYPOINT ["/traefik"]
# Thu, 02 Aug 2018 21:03:47 GMT
RUN cmd /S /C #(nop)  LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.7.0-rc3 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:d4a9b16fd154d065649f42ee7ac674690d46dbe6ad2398a58166c37c85ca64ed`  
		Last Modified: Tue, 10 Jul 2018 21:16:01 GMT  
		Size: 166.8 MB (166830055 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c3ea19ea6b03dcb1211fddcb998dade45d1eb8e42232e8b6f012291e855a6375`  
		Last Modified: Thu, 02 Aug 2018 21:04:08 GMT  
		Size: 16.0 MB (16037997 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:24aee5bbce57fa9e00c91452ab278e4f330bd25114a41e944bfd60c6eda2d4ac`  
		Last Modified: Thu, 02 Aug 2018 21:04:02 GMT  
		Size: 951.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04ac009076ae9d376698f7361bb9f9ee1b2e5d6a18cde860c7ad25c652311f5c`  
		Last Modified: Thu, 02 Aug 2018 21:04:02 GMT  
		Size: 950.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c2d2ca0b425d5ef3888da73e430a09e2446a6d44992e93e847dd516fe6cde7b`  
		Last Modified: Thu, 02 Aug 2018 21:04:02 GMT  
		Size: 952.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8398ea397103ea2ee319e81fa5748fe1f944010da554bff6ae41dbd2f95968d3`  
		Last Modified: Thu, 02 Aug 2018 21:04:02 GMT  
		Size: 953.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9815151f086672644508ddff047f127c20cf9c88a95be6b0705eae0f8897002`  
		Last Modified: Thu, 02 Aug 2018 21:04:02 GMT  
		Size: 948.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
