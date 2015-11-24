# myDockerFiles
Docker files for my projects.

Contains Docker files for creating centos base O.S. with Tomcat 6, 7 and 8 with Oracle JDK 6, 7 and 8. Also contain vim installed and the JAVA_HOME enviroment variable.

Create image: 
docker build -t tomcat8djk8 .
docker build -t tomcat6djk6 .

Create an run a container:
docker run -it -d --name catContainer6 -p 8080:8080 yourDockerRegistry:5000/tomcat6jdk6:latest /srv/Tomcat6/apache-tomcat-6.0.44/bin/catalina.sh run
