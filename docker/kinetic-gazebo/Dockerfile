FROM roscloud:kinetic

# Install gazebo packages
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D2486D2DD83DB69272AFE98867170598AF249743 && \
	echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list && \	
	apt-get update && \
	apt-get install -y --no-install-recommends \
		ros-kinetic-gazebo-ros-pkgs ros-kinetic-gazebo-ros-control && \
    apt-get clean && \
	rm -rf /var/lib/apt/lists/* 

# Install gzweb dependent packages
RUN apt-get update && \
	apt-get purge -y git && \
	apt-get install -y \
	libjansson-dev nodejs npm nodejs-legacy libboost-dev imagemagick libtinyxml-dev mercurial cmake build-essential git && \
    apt-get clean && \
	rm -rf /var/lib/apt/lists/* 
	
# clone gzweb
ENV GZWEB_WS /root/gzweb
ADD gzweb_1.4.0 $GZWEB_WS
WORKDIR $GZWEB_WS
