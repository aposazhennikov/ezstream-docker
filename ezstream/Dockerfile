FROM debian:latest

COPY ezstream_1.0.1-1_amd64.deb /etc/ezstream/ezstream_1.0.1-1_amd64.deb
COPY ezstream.xml /etc/ezstream/ezstream.xml
 
RUN apt-get update && apt-get upgrade -y && \
apt-get install zlib1g-dev libutfcpp-dev libxml2 curl ffmpeg lame libiconv-hook-dev \
libtool check checkinstall software-properties-common libxml2-dev \
build-essential libcurl4-openssl-dev libxslt1-dev libxml2-dev libogg-dev \
libvorbis-dev libflac-dev libtheora-dev libssl-dev libspeex-dev pkg-config \
ezstream -y && ls -la /etc/ezstream && dpkg -i "/etc/ezstream/ezstream_1.0.1-1_amd64.deb" && \
apt-mark hold ezstream && apt-get clean && \
rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


CMD ["/usr/bin/ezstream", "-c", "/etc/ezstream/ezstream.xml"]


