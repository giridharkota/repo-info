## `kong:latest`

```console
$ docker pull kong@sha256:e5b1cfb2107d2a4018b1364536fdd4af7d2755962a2c53ddd966b27c7680b962
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `kong:latest` - linux; amd64

```console
$ docker pull kong@sha256:effa9a68317ff2ab0e384fbccaae75213e89cd7909a054a819de90349351942a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **33.6 MB (33564000 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0423fe5663fcb29c83f3bff1ee0064ab200a4b7d1e38e4dd7b2122a6caa2bc00`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["kong","docker-start"]`

```dockerfile
# Fri, 06 Jul 2018 14:13:25 GMT
ADD file:eceadb32d029164d23db918d14c88df7186b6ee9645fa2f0c0a7e3e046a6a129 in / 
# Fri, 06 Jul 2018 14:13:25 GMT
CMD ["/bin/sh"]
# Sat, 07 Jul 2018 03:44:49 GMT
LABEL maintainer=Marco Palladino, marco@mashape.com
# Sat, 07 Jul 2018 03:44:49 GMT
ENV KONG_VERSION=0.14.0
# Sat, 07 Jul 2018 03:44:50 GMT
ENV KONG_SHA256=968b355f6e46218dee31497f65fd708cf219b096c1c54bff7da00efb0c2db520
# Sat, 07 Jul 2018 03:45:02 GMT
RUN apk add --no-cache --virtual .build-deps wget tar ca-certificates 	&& apk add --no-cache libgcc openssl pcre perl tzdata curl 	&& wget -O kong.tar.gz "https://bintray.com/kong/kong-community-edition-alpine-tar/download_file?file_path=kong-community-edition-$KONG_VERSION.apk.tar.gz" 	&& echo "$KONG_SHA256 *kong.tar.gz" | sha256sum -c - 	&& tar -xzf kong.tar.gz -C /tmp 	&& rm -f kong.tar.gz 	&& cp -R /tmp/usr / 	&& rm -rf /tmp/usr 	&& cp -R /tmp/etc / 	&& rm -rf /tmp/etc 	&& apk del .build-deps
# Sat, 07 Jul 2018 03:45:03 GMT
COPY file:e1ac3f3f858d8725b7a4bbe2a68d491ba6f524d0d6384516d5f0ce50d28b9fda in /docker-entrypoint.sh 
# Sat, 07 Jul 2018 03:45:03 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 07 Jul 2018 03:45:04 GMT
EXPOSE 8000/tcp 8001/tcp 8443/tcp 8444/tcp
# Sat, 07 Jul 2018 03:45:04 GMT
STOPSIGNAL [SIGTERM]
# Sat, 07 Jul 2018 03:45:04 GMT
CMD ["kong" "docker-start"]
```

-	Layers:
	-	`sha256:a073c86ecf9e0f29180e80e9638d4c741970695851ea48247276c32c57e40282`  
		Last Modified: Fri, 06 Jul 2018 14:16:26 GMT  
		Size: 2.0 MB (2014658 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe9db5a53243089eee0256ac935d0d650755f05b17e419d6e6e0fe2f09ef452b`  
		Last Modified: Sat, 07 Jul 2018 03:48:57 GMT  
		Size: 31.5 MB (31549028 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0cdea2e533866fe120db80ba618785b29d0655593230e8e5d882c6e6d7ccd35b`  
		Last Modified: Sat, 07 Jul 2018 03:48:45 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
