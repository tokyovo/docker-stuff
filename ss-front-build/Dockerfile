FROM ubuntu:16.04
RUN apt-get update && apt-get install -y software-properties-common

# Install Java.
RUN \
  echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  add-apt-repository -y ppa:webupd8team/java && \
  apt-get update && \
  apt-get install -y oracle-java8-installer && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk8-installer

# install postgres && postgis
RUN apt-get update
RUN apt-get install -y postgresql-9.5 postgresql-contrib-9.5 postgresql-9.5-postgis-2.2

# debuild stuff
RUN apt-get install -y dh-make devscripts build-essential lintian ant debhelper


# Define working directory.
WORKDIR /sensen

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle