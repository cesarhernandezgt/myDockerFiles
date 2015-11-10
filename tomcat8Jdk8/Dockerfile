# TOMCAT 8.0.24 AND JDK 8 update 51

FROM centos:latest
MAINTAINER cesar hernandez <https://twitter.com/cesarHgt>

#Install vim
RUN yum install -y vim && echo Finalizo instalacion vim.


# JDK 8 update 51, Download, unzip, delete targz
ENV JRE_DIR /usr/jre
ENV ORACLE_JDK_URL  http://download.oracle.com/otn-pub/java/jdk/8u51-b16/server-jre-8u51-linux-x64.tar.gz
RUN mkdir -p "$JRE_DIR"
WORKDIR $JRE_DIR

RUN curl -sSf -L --cookie "oraclelicense=accept-securebackup-cookie" "$ORACLE_JDK_URL" > jdk.tar.gz \
        && tar zxvf jdk.tar.gz \
        && rm jdk.tar.gz \
        && echo Finalizo instalacion jdk.


# TOMCAT 8.0.24 Dowload, unzip, delete zip and tomcat .bat files
ENV TOMCAT_8_HOME /srv/Tomcat8
RUN mkdir -p "$TOMCAT_8_HOME"
WORKDIR $TOMCAT_8_HOME
ENV TOMCAT_URL http://www.motorlogy.com/apache/tomcat/tomcat-8/v8.0.24/bin/apache-tomcat-8.0.24.tar.gz

RUN curl -sSf -L "$TOMCAT_URL" > tomcat8.tar.gz \
        && tar xvf tomcat8.tar.gz \
        && rm tomcat8.tar.gz \
        && rm apache-tomcat-8.0.24/bin/*.bat \
        && echo Finalizo instalacion tomcat. 
		
RUN echo "export JAVA_HOME=/usr/jre/jdk1.8.0_51" > apache-tomcat-8.0.24/bin/setenv.sh \
        && echo Fializo creacion de setenv.sh asignando JAVA_HOME 

# abrimos bash
CMD ["/bin/bash"]

# clean yum cache
# yum clean all

#Si se quisiera automaticamente inicar el servidor, descomentar lo siguiente:
#EXPOSE 8080
#CMD ["catalina.sh", "run"]

