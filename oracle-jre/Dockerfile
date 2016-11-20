FROM centos:7

MAINTAINER sdi

# Build time arguments
ARG JAVA_VERSION=${jre_version:-8u112}
ARG JAVA_VERSION_BUILD=${jre_version_build:-b15}

RUN yum update -y && \
yum install -y wget && \
wget --no-cookies --no-check-certificate \
  --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" \
   "http://download.oracle.com/otn-pub/java/jdk/$JAVA_VERSION-$JAVA_VERSION_BUILD/jre-$JAVA_VERSION-linux-x64.rpm" && \
yum localinstall -y /jre-$JAVA_VERSION-linux-x64.rpm && \
rm -f /jre-8u112-linux-x64.rpm && \
yum clean all

# Set environment variables
ENV HOME /root

# Define working directory
WORKDIR /root

# Define default command
CMD ["bash"]
