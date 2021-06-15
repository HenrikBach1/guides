# Run Docker commands without sudo

##### Add the `docker` group if it doesn't already exist

```console
$ sudo groupadd docker
```

##### Add the connected user `$USER` to the docker group

Optionally change the username to match your preferred user.

```console
$ sudo gpasswd -a $USER docker
```

##### Add `docker` socket to `docker` group:

```console
$ sudo ls -halt /var/run/docker.sock
$ sudo chgrp docker /var/run/docker.sock
$ newgrp docker
$ groups
```

##### Restart the `docker` daemon

```console
$ sudo service docker restart
```
or
```console
$ sudo systemctl restart snap.docker.dockerd.service
```

If you are on Ubuntu 14.04-15.10, use `docker.io` instead:

```console
$ sudo service docker.io restart
```
