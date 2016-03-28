# CentOS 6.5 + sshd

```sh
# Pull and Run
$ docker pull komukomo/centos-sshd:6.5
$ IMAGENAME=yourimagename
$ docker run -d --name $IMAGENAME komukomo/centos-sshd:6.5

# SSH Access
$ IP=$(docker inspect  -f "{{.NetworkSettings.IPAddress}}" $IMAGENAME)
$ ssh $IP -l root
root@${IP}'s password: root
```
