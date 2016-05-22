# RPMBUILD

## Example of Use

```
$ CONTAINER="container_name"
$ docker run -d --name $CONTAINER komukomo/rpmbuild
$ IP=$(docker inspect -f "{{.NetworkSettings.IPAddress}}" $CONTAINER)
$ ssh $IP -lroot
root@[$IP]s password: root
-bash-4.1 # yumdownloader --source httpd
-bash-4.1 # rpm -ivh httpd-2.2.15-31.el6.centos.src.rpm
-bash-4.1 # vi rpmbuild/SPECS/httpd.spec # edit...
-bash-4.1 # rpmbuild -ba rpmbuild/SPECS/httpd.spec
# You may need to install some dependencies.
-bash-4.1 # ls rpmbuild/RPMS/x86_64/
httpd-devel-2.2.15-31.el6.x86_64.rpm
...

```

