FROM tomcat:9.0
# Define WorkDir
WORKDIR /usr/local/tomcat
# ADD .war to WorkDir
ADD --chown=tomcat:tomcat ../artifacts/ROOT.war /usr/local/tomcat/webapps
# Start Tomcat
CMD ["catalina.sh","run"]
