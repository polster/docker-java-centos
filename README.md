CentOS 7 with Java
==================

## Intro

### Purpose

This code project contains some Dockerfiles to be used to build a Java version XYZ powered CentOS 7 image.

### Available Java Versions

The following versions are currently available (identified by Docker tag):

* oracle-8-jre

### Dev guidelines

* Github: In case of a new Java version update or any other relevant change to the code project to be released, a new Git tag will be created
* Docker Cloud:
  * The latest commit will trigger a new image build of all Java versions available (e.g. [oracle8-jre](oracle8-jre)), representing the Git master and runnable as Docker container by simply specifying the implicit Docker tag (e.g. oracle-jre-8)
  * A new Git tag will result in a new image build of all Java versions available, represented by an explicit Docker tag containing the Git tag version as well (e.g. oracle-jre-8-1.0.0)

## User Manual

## Build

* Builds are being created automatically. See the [java-centos7 repo builds](https://cloud.docker.com/app/polster/repository/docker/polster/java-centos7/builds) on Docker Cloud for more details
* In case you want to build your own images, do the following (for instance to build Oracle JRE 8, update 101):
```
# Clone the source project
git clone https://github.com/polster/docker-java-centos.git

# Cd into the the folder representing the required Java version
cd docker-java-centos/oracle8-jre

# Build the image by specifying an explicit Java version
docker build --build-arg JAVA_VERSION=8u101 --build-arg JAVA_VERSION_BUILD=b13 -tag oracle-jre-8-101 .

```

### Run

* Run the following command in order to start an Oracle JRE 8 container based on the latest Git master build:
```
docker run -ti polser/java-centos7:oracle-jre-8
```
* Run the following command in order to start an Oralce JRE 8 container based on one of the available Git tag versions bound to a specific JRE version update:
```
docker run -ti polser/java-centos7:oracle-jre-8-1.0.0
```
