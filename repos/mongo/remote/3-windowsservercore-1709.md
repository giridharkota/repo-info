## `mongo:3-windowsservercore-1709`

```console
$ docker pull mongo@sha256:9f6e8e9cd250b308d8383342b7c62b71ffcfdc6fa1db78ba10e035ada3974d9b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.16299.611; amd64

### `mongo:3-windowsservercore-1709` - windows version 10.0.16299.611; amd64

```console
$ docker pull mongo@sha256:79c7d67c6cf77a9ac10a15f905520d4dec0d14ffdf3307e281bf92bf389d1de1
```

-	Docker Version: 17.06.2-ee-13
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.7 GB (3650455792 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b8bdd1a4630a8b4f5f105cd466dd79b373fc6ff96a0e09e47c0357e5ca157c01`
-	Default Command: `["mongod","--bind_ip_all"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Wed, 08 Aug 2018 23:20:54 GMT
RUN Install update 10.0.16299.611
# Fri, 17 Aug 2018 09:24:21 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Fri, 17 Aug 2018 09:39:56 GMT
ENV MONGO_VERSION=3.6.6
# Fri, 17 Aug 2018 09:39:57 GMT
ENV MONGO_DOWNLOAD_URL=https://downloads.mongodb.org/win32/mongodb-win32-x86_64-2008plus-ssl-3.6.6-signed.msi
# Fri, 17 Aug 2018 09:39:57 GMT
ENV MONGO_DOWNLOAD_SHA256=584bc98ce5755f419b7182c3abf1c632a4365e28577a4f498be2c291beeae7c2
# Fri, 17 Aug 2018 09:58:52 GMT
RUN Write-Host ('Downloading {0} ...' -f $env:MONGO_DOWNLOAD_URL); 	(New-Object System.Net.WebClient).DownloadFile($env:MONGO_DOWNLOAD_URL, 'mongo.msi'); 		Write-Host ('Verifying sha256 ({0}) ...' -f $env:MONGO_DOWNLOAD_SHA256); 	if ((Get-FileHash mongo.msi -Algorithm sha256).Hash -ne $env:MONGO_DOWNLOAD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'mongo.msi', 			'/quiet', 			'/qn', 			'INSTALLLOCATION=C:\mongodb', 			'ADDLOCAL=all' 		); 	$env:PATH = 'C:\mongodb\bin;' + $env:PATH; 	[Environment]::SetEnvironmentVariable('PATH', $env:PATH, [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  mongo --version'; mongo --version; 	Write-Host '  mongod --version'; mongod --version; 		Write-Host 'Removing ...'; 	Remove-Item C:\mongodb\bin\*.pdb -Force; 	Remove-Item C:\windows\installer\*.msi -Force; 	Remove-Item mongo.msi -Force; 		Write-Host 'Complete.';
# Fri, 17 Aug 2018 09:58:54 GMT
VOLUME [C:\data\db C:\data\configdb]
# Fri, 17 Aug 2018 09:58:56 GMT
EXPOSE 27017/tcp
# Fri, 17 Aug 2018 09:58:57 GMT
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
	-	`sha256:6bf6816aaf59c0f07a4e05da584c6f7ffd5bb1b88857d1b2a24752229d722acd`  
		Last Modified: Fri, 17 Aug 2018 11:38:28 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dff2a77315c980fc8da6840e1600fa9d1142aa145cf7121dae87f69f08d30035`  
		Last Modified: Fri, 17 Aug 2018 11:38:27 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:afd5339b2551196f141fa5346a4108a2a3d4a100fb608d372c690a9e422b967f`  
		Last Modified: Fri, 17 Aug 2018 11:38:25 GMT  
		Size: 1.2 KB (1207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c54ed76500887df1504bcf67fcb031298a1593ad861d92a6f79fcb4dcb6e2171`  
		Last Modified: Fri, 17 Aug 2018 11:39:29 GMT  
		Size: 538.3 MB (538311680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fb197b4854efcb4bbee22afc60cf1fb20a51bcc1b1cffc28e85c6888200e896`  
		Last Modified: Fri, 17 Aug 2018 11:38:25 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:729482620dd2198dab11438727cc50e717b1fddcad67d09fd4fffb500055d6e3`  
		Last Modified: Fri, 17 Aug 2018 11:38:25 GMT  
		Size: 1.2 KB (1203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6adf24a0727d94d5d8cd3e44983c2e045c998176364da5a1bfb8517e81d0a3a`  
		Last Modified: Fri, 17 Aug 2018 11:38:25 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
