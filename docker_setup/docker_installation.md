Ref: [Docker CLI Installation doc](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

```
# Add Docker's official GPG key:

$ sudo apt update  
$ sudo apt-get install ca-certificates curl
$ sudo install -m 0755 -d /etc/apt/keyrings
$ sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
$ sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:

$ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
$ sudo apt update
```

Installing the Docker packages

```
$  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Verify the installation by downloading and running and `Hello World` program.

```
$ sudo docker run hello-world
```
The command downloads tries to run a test image called `hello-world` and runs it in a container. So, first the command checks whether there is an image with same name in the local image repo. If not, it downloads the image from Docker Hub. If the command is successfull, you can see a message with `Hello from Docker! ...`

### Post installation steps [[ref.](https://docs.docker.com/engine/install/linux-postinstall/)]

This is mainly for Linux and DIY installation.

#### Manage Docker as a non-root user

> [! WARNING]
> Users who runs need `root` privilege which could be an isssue if it is in a shared server.

To create a `docker` group and add your user:
1. Create the `docker` group
```
$ sudo groupadd docker
```

2. Add your user to the `docker` group:
```
$ sudo usermod -aG docker $USER
```
3. Verify the setup by running the `hello-world` without `sudo`
```
$ docker run hello-world
```
