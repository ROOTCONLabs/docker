# Tested on macOS

FROM kalilinux/kali-rolling:latest

LABEL maintainer="semprix@rootcon.org"

ENV DEBIAN_FRONTEND noninteractive
ENV TERM xterm-256color

RUN apt-get -y update
RUN apt-get -y install kali-tools-top10 exploitdb man-db dirb nikto wpscan uniscan

# Because Daniel Miessler is awesome!
RUN git clone https://github.com/danielmiessler/SecLists /usr/share/seclists

# Clean Up
RUN apt-get autoremove -y && apt-get clean 

# Welcome message
RUN echo "echo 'Welcome to Docker Kali from ROOTCONLabs'" >> /etc/profile

# Install Hamachi for internal testing via Hamachi VPN
# WORKDIR /root
# wget https://www.vpn.net/installers/logmein-hamachi_2.1.0.203-1_amd64.deb
# RUN dpkg -i logmein-hamachi_2.1.0.203-1_amd64.deb
# RUN hamachi login
# RUN hamachi attach <email-address>
# RUN hamachi join <network-id>
