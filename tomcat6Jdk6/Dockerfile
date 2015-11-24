# TOMCAT 6.0.44 AND JDK 6 update 45 (jdk already has to be present befor image build)

FROM centos:latest
MAINTAINER cesar hernandez <https://twitter.com/cesarHgt>

#Install vim
RUN yum install -y vim && echo Finalizo instalacion vim.


# JDK 6 update 45, Download, unzip, delete targz
ENV JRE_DIR /usr/jre
RUN mkdir -p "$JRE_DIR"
WORKDIR $JRE_DIR

#You need to provide the jdk.bin file (orginaly named jdk-6u45-linux-x64.bin) in the same direcotory level than this DockerFile
ADD jdk.bin /usr/jre/
RUN ./jdk.bin \
        && rm jdk.bin \
        && echo Finalizo instalacion jdk.


# TOMCAT 6.0.44 Dowload, unzip, delete zip and tomcat .bat files
ENV TOMCAT_6_HOME /srv/Tomcat6
RUN mkdir -p "$TOMCAT_6_HOME"
WORKDIR $TOMCAT_6_HOME
ENV TOMCAT_URL http://www.eu.apache.org/dist/tomcat/tomcat-6/v6.0.44/bin/apache-tomcat-6.0.44.tar.gz

RUN curl -sSf -L "$TOMCAT_URL" > tomcat.tar.gz \
        && tar xvf tomcat.tar.gz \
        && rm tomcat.tar.gz \
        && rm apache-tomcat-6.0.44/bin/*.bat \
        && echo Finalizo instalacion tomcat. 

RUN echo "export JAVA_HOME=/usr/jre/jdk1.6.0_45" > apache-tomcat-6.0.44/bin/setenv.sh \
        && echo Fializo creacion de setenv.sh asignando JAVA_HOME 

# abrimos bash
CMD ["/bin/bash"]