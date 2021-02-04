FROM ubuntu:latest
ARG last_name
MAINTAINER Ashish
RUN apt-get update
ENV name Ashish
ENV second_name $last_name 
ENTRYPOINT echo "Hello, $name $second_name"
