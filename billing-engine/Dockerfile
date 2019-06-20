FROM tomcat:7-jdk8-slim
COPY webapp /usr/local/tomcat/webapps
COPY client-truststore.jks /usr/local/tomcat
EXPOSE 8080
CMD ["catalina.sh", "run"]
