# base image: fedora
FROM fedora:latest

# check and install latest packages
RUN dnf update -y

# install java openjdk, multiple versions = more variability
RUN dnf install java-11-openjdk java-17-openjdk java-1.8.0-openjdk -y

# enable polymc repo and install polymc
#RUN dnf copr enable polymc/polymc
RUN dnf install wget -y
RUN wget https://copr.fedorainfracloud.org/coprs/polymc/polymc/repo/fedora-39/polymc-polymc-fedora-39.repo -O /etc/yum.repos.d/polymc-polymc-fedora-39.repo
RUN dnf check-update && dnf install polymc -y

# add new user
RUN adduser -m -s /bin/bash myUser
RUN gpasswd -a myUser video
RUN gpasswd -a myUser audio
RUN gpasswd -a myUser input
RUN gpasswd -a myUser tty
USER myUser

# run polymc
CMD [ "polymc" ]