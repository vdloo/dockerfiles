# build hhvm in Debian Jessie

FROM tianon/debian:jessie

RUN apt-get update && \
	apt-get -y upgrade && \
	apt-get -y install \
	autoconf \
	automake \
	binutils \
	binutils-dev \
	build-essential \
	cmake \
	cmake-data  \
	cpp  \
	g++  \
	g++-4.8 \
	gcc  \
	gcc-4.8 \
	git \
	libacl1  \
	libarchive13  \
	libattr1 \
	libboost-filesystem1.55-dev  \
	libboost-program-options1.55-dev \
	libboost-regex1.55-dev \
	libboost-system1.55-dev \
	libboost-thread-dev \
	libboost-thread1.55.0 \
	libbz2-dev \
	libc-bin \
	libc-client2007e-dev \
	libc-dev-bin \
	libc6 \
	libc6-dev \
	libcap-dev \
	libcloog-ppl-dev \
	libcurl4-openssl-dev \
	libdwarf-dev \
	libelf-dev \
	libevent-dev  \
	libgcc1 \
	libgd2-xpm-dev \
	libgomp1 \
	libgoogle-glog-dev \
	libgoogle-perftools-dev \
	libiberty-dev \
	libicu-dev \
	libjemalloc-dev \
	libkrb5-dev \
	libldap2-dev  \
	libmagickwand-dev \
	libmcrypt-dev \
	libmemcached-dev \
	libmpfr4 \
	libmysqlclient-dev \
	libncurses5-dev \
	libonig-dev \
	libpcre3-dev \
	libreadline-dev \
	libstdc++-4.8-dev \
	libstdc++6 \
	libtbb-dev \
	libtbb2 \
	libtool \
	libunwind8-dev \
	libxml2-dev \
	libxslt-dev  \
	make  \
	memcached \
	openssl \
	php5-imagick \
	php5-mcrypt \
	pkg-config \
	subversion \
	wget \
	zlib1g-dev

RUN git clone git://github.com/facebook/hhvm.git /home/hhvm 

RUN cd /home/hhvm ; \
	export CMAKE_PREFIX_PATH=`pwd` ; \
	git submodule update --init --recursive ; \
	cmake . ; \
	make
