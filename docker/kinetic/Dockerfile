FROM ros:kinetic-robot

# Install shellinabox packages
RUN apt-get update && \
	apt-get install -y \
		openssl curl openssh-client sudo shellinabox && \
    apt-get clean && \
	rm -rf /var/lib/apt/lists/* 

# Create a user for shellinabox access
RUN groupadd -g 1000 user && \
	useradd -u 1000 -g 1000 -s /bin/bash -d /home/user -m user && \
	echo "user:7355608" | chpasswd && \
	usermod -aG sudo user

EXPOSE 4200
VOLUME /home/user

# Remove -t when HTTPS implemented
CMD shellinaboxd -t