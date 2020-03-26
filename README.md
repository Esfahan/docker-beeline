# docker-beeline

## Installation
Prepare the files below and put into the each dir.

- files/krb5/krb5.conf
- files/hadoop/core-site.xml
- files/secrets/keytab
- files/secrets/ca-bundle.crt

## Build

### CentOS

```
$ sudo docker build -f Dockerfile_centos -t beeline-centos ./
```

### Debian

```
$ sudo docker build -f Dockerfile_debian -t beeline-debian ./
```

## Usage
### CentOS

```
$ sudo docker run --rm -it beeline-centos /bin/bash
[root@df7599e76bcb src]# kinit -kt /secrets/keytab username
[root@df7599e76bcb src]# beeline -u 'jdbc:hive2://example.com:10000/;principal=hive/example.com@EXAMPLE.COM;saslQop=auth-conf;useUnicode=true;characterEncoding=utf8;'
```

### Debian

```
$ sudo docker run --rm -it beeline-debian /bin/bash
[root@df7599e76bcb src]# kinit -kt /secrets/keytab username
[root@df7599e76bcb src]# beeline -u 'jdbc:hive2://example.com:10000/;principal=hive/example.com@EXAMPLE.COM;saslQop=auth-conf;useUnicode=true;characterEncoding=utf8;'
```
