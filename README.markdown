### Getting started with docker on Windows

1. Install Docker https://docs.docker.com/docker-for-windows/install/ via IT as it requires Administrator Permissions
2. Request IT to add your user to docker-users group
3. Restart Laptop
4. Start Docker Desktop
5. Wait a few minutes ...
6. While waiting go to http://hub.docker.com and make an account
7. Go to the command prompt login following command
    ```
    docker login
    # Enter username Note: its different from email address
    # Enter password
    ```
8. Open terminal and verify the version of docker
    ```
    docker version
    ```
    ```
    Client: Docker Engine - Community
    Version:           18.09.2
    API version:       1.39
    Go version:        go1.10.8
    Git commit:        6247962
    Built:             Sun Feb 10 04:12:31 2019
    OS/Arch:           windows/amd64
    Experimental:      false

    Server: Docker Engine - Community
    Engine:
    Version:          18.09.2
    API version:      1.39 (minimum version 1.12)
    Go version:       go1.10.6
    Git commit:       6247962
    Built:            Sun Feb 10 04:13:06 2019
    OS/Arch:          linux/amd64
    Experimental:     false
    ```
9. Hello world example
    ```
    docker run hello-world
    ```
    ```
    Hello from Docker!
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
    1. The Docker client contacted the Docker daemon.
    2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
    ...
    ```
10. Run interactive Ubuntu
    ```
    docker run -it ubuntu bash
    ```
    ```
    Unable to find image 'ubuntu:latest' locally
    latest: Pulling from library/ubuntu
    7413c47ba209: Pull complete
    0fe7e7cbb2e8: Pull complete
    1d425c982345: Pull complete
    344da5c95cec: Pull complete
    Digest: sha256:c303f19cfe9ee92badbbbd7567bc1ca47789f79303ddcef56f77687d4744cd7a
    Status: Downloaded newer image for ubuntu:latest
    root@4b78a9a4f661:/# uname -a
    Linux 4b78a9a4f661 4.9.125-linuxkit #1 SMP Fri Sep 7 08:20:28 UTC 2018 x86_64 x86_64 x86_64 GNU/Linux
    ```
11. Update docker 
12. Optional allow firewall for vpnkit.exe
13. Enable kubernetes in the settings
