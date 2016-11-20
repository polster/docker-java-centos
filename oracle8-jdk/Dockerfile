FROM centos:7

MAINTAINER sdi

# Build time arguments
ARG JAVA_VERSION=${jdk_version:-8u112}
ARG JAVA_VERSION_BUILD=${jdk_version_build:-b15}

RUN yum update -y && \
yum install -y wget && \
wget --no-cookies --no-check-certificate \
  --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" \
   "http://download.oracle.com/otn-pub/java/jdk/$JAVA_VERSION-$JAVA_VERSION_BUILD/jdk-$JAVA_VERSION-linux-x64.rpm" && \
yum localinstall -y /jdk-$JAVA_VERSION-linux-x64.rpm && \
rm -f /jdk-8u112-linux-x64.rpm && \
yum clean all

# Set environment variables
ENV HOME /root

# Define working directory
WORKDIR /root

# Define default command
CMD ["bash"]
