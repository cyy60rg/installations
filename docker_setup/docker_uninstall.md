### Uninstall Docker Engine

1. Uninstall the Docker Engine, CLI, containerd, and Docker Compose packages:
```
$ sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
```

2. Images, containers, volumes, or custom configuration files on your host aren't automatically removed. To delete all images, containers, and volumes:
```
$ sudo rm -rf /var/lib/docker
$ sudo rm -rf /var/lib/containerd
```

3. Remove source list and keyrings
```
$ sudo rm /etc/apt/sources.list.d/docker.list
$ sudo rm /etc/apt/keyrings/docker.asc
```

You have to delete any edited config. files eg. firewall, manually.

