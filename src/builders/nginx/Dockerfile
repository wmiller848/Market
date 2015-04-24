#
FROM fedora:latest

# Set up deps
RUN yum install -y glibc-devel glibc-headers glibc-static
RUN yum install -y gcc cpp pcre-devel
RUN yum install -y openssl-devel
RUN yum install -y git mercurial
RUN yum install -y git tar wget
RUN yum install -y cmake make autoconf

# Download nginx and rtmp module
WORKDIR /opt/vendor
RUN wget http://nginx.org/download/nginx-1.7.12.tar.gz
RUN git clone https://github.com/arut/nginx-rtmp-module.git
RUN tar -xvpzf nginx-1.7.12.tar.gz

# Install nginx
WORKDIR /opt/vendor/nginx-1.7.12
RUN ./configure --with-http_spdy_module --with-http_ssl_module --with-http_secure_link_module --with-http_gzip_static_module --with-http_gunzip_module --add-module=/opt/vendor/nginx-rtmp-module
RUN make install
WORKDIR /opt

EXPOSE 80
CMD nginx
