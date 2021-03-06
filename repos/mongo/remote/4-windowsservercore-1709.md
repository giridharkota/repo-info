## `mongo:4-windowsservercore-1709`

```console
$ docker pull mongo@sha256:56d040ae21d4ec72d1b0d9644b774653b3e42a28405c4b0bc40b3a0d729072cc
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.16299.611; amd64

### `mongo:4-windowsservercore-1709` - windows version 10.0.16299.611; amd64

```console
$ docker pull mongo@sha256:7a60bbc2ce17280c1a7846b452b697b4195f2f4a073f44de9d14749fc0f1362f
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.6 GB (3644056628 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7488bbb46e80effae86d9b8913da1d6989e71513c14f961b8f8b985e8d6cf9d2`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Wed, 08 Aug 2018 23:20:54 GMT
RUN Install update 10.0.16299.611
# Fri, 17 Aug 2018 09:24:21 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Fri, 17 Aug 2018 10:05:28 GMT
ENV MONGO_VERSION=4.0.1
# Fri, 17 Aug 2018 10:05:29 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2008plus-ssl-4.0.1-signed.msi
# Fri, 17 Aug 2018 10:05:30 GMT
ENV MONGO_DOWNLOAD_SHA256=234bebe451ca4601a8fd5016ede6b3ad424ac059dfcb3d0e76abf934f4143af4
# Fri, 17 Aug 2018 10:24:58 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 17 Aug 2018 10:25:00 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 17 Aug 2018 10:25:03 GMT
EXPOSE 27017/tcp
# Fri, 17 Aug 2018 10:25:04 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c4047f78756c2319eb99557ec7139906cf11af6c91aefcc0e44ac49a5481d8e4`  
		Last Modified: Mon, 13 Aug 2018 18:28:41 GMT  
		Size: 837.8 MB (837835144 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:979b51c3a12a3db81990ebd92c5d5a3325e035f84c0503e987ede3bfd73f44df`  
		Last Modified: Fri, 17 Aug 2018 11:36:35 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:490d3e78be7dd54cf05a1933eb26d28162a0ef119fb9f5e4a9b0fb0dcdacd29e`  
		Last Modified: Fri, 17 Aug 2018 11:40:33 GMT  
		Size: 1.2 KB (1187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b1710f9bc4b79d025d93e70b34c7d748ce328c581162bf5ec5c13d7dd0381e81`  
		Last Modified: Fri, 17 Aug 2018 11:40:32 GMT  
		Size: 1.2 KB (1181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67f6feb6722d34e1a402cfe5b9eff7029447c8d6ba0ce5ccd8d17624a152c399`  
		Last Modified: Fri, 17 Aug 2018 11:40:30 GMT  
		Size: 1.2 KB (1202 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d05a7db5c13c8fe61ca8391c3a448d41d15b61efba97fcaa5fef9b1f1acaf8ba`  
		Last Modified: Fri, 17 Aug 2018 11:41:37 GMT  
		Size: 531.9 MB (531912563 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa45127ee9397c17546b43ed5367b008bc13ce43977db82db76e1a5929f7e295`  
		Last Modified: Fri, 17 Aug 2018 11:40:30 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:889a5739e14acf587823ae98ea1cd810a24f924158b61298fb4ba447fc1de2a0`  
		Last Modified: Fri, 17 Aug 2018 11:40:31 GMT  
		Size: 1.2 KB (1187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90ab75760418c50d5b65ae0e38c90b048064d6aaa951cf815637fd5b2b88b2f3`  
		Last Modified: Fri, 17 Aug 2018 11:40:30 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
