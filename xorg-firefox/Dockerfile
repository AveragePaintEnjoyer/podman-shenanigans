# base image: fedora
FROM fedora:latest

# check and install latest packages + install firefox
RUN dnf update -y && dnf install firefox -y

# run firefox
CMD [ "firefox" ]