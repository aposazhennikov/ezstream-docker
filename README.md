# ezStream Politics Radio Broadcasting

This repository contains the Docker setup for running an ezStream radio broadcasting service focused on politics. It uses `ezstream`, an open-source command-line source client for Icecast media streaming servers, to stream audio content over the internet.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- You have a **Linux-based host** with Docker/Docker compose and Git installed.
- You have a basic understanding of Docker and Docker Compose.
- You have cloned the repository to your local machine or server.

## Installation

To get started with `ezstream`, clone this repository and navigate into the directory:

```
git clone https://github.com/aposazhennikov/ezstream-docker.git
cd ezstream-docker
```
Configuration
Modify the ezstream.xml configuration file according to your streaming server details. You will need to specify the hostname, URL, password, and other stream settings.

Building and Running
Build and run the Docker container using Docker Compose:


```
mkdir -p /home/ezstream
docker-compose up --build
```
This command will build the Docker image using the Dockerfile in the ezstream directory and tag it as ezstream:latest. 
The container will be named ezstream_politics and will use the host's network.

You should also add some music files which you would like to stream to the /home/ezstream directory and create playlist.
```
find /home/ezstream -type f -name "*.mp3" | tee -a /home/ezstream/playlist.txt
```

Volumes
The service uses a bind mount volume to link the host directory /home/ezstream to the container's directory /home/ezstream. This allows you to manage your playlists and other necessary files directly from the host.

Usage
Once the container is running, ezstream will start broadcasting based on the provided ezstream.xml configuration. You can manage your playlists and audio files in the specified intake directory.
You may want to change ip adress in ezstream.xml if your Icecast is not on the same server as an ezstream otherwise you can leave it as it is.

Contributing
Contributions to this project are welcome. You can help by:

Reporting a bug
Suggesting enhancements
Submitting a pull request with improvements

Contact
If you have any questions or feedback, please contact [Aleksandr] at [aposazhennikoff@gmail.com].

Thank you for using or contributing to ezstream.





