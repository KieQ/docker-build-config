# Base images is ubuntu latest, which is of version 20.04
FROM ubuntu:latest

LABEL name="kieq_build"

LABEL author="kie"

LABEL language="cpp, python"

WORKDIR /root

ARG DEBIAN_FRONTEND=noninteractive

ENV TZ=Asia/Shanghai

# Install C++, Python and Golang with other tools
RUN apt update && apt install -y g++ cmake gdb git python3 python3-pip golang-go curl unzip

# Install conan
RUN pip install conan && conan profile new default --detect && conan profile update settings.compiler.libcxx=libstdc++11 default

# Install Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && apt-get install -y nodejs

