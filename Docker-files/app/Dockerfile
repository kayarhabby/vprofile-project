# fetch the image openjdk:11 on dockerhub as build_image
# this image will be used to build the image with maven 
FROM openjdk:11 AS BUILD_IMAGE
# run command
RUN apt update && apt install maven -y
RUN git clone https://github.com/kayarhabby/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

# fetch the image tomcat:9-jre on dockerhub as build_image
FROM tomcat:9-jre11
# label 
LABEL "Project"="Vprofile"
LABEL "Author"="Rhabby"
# run command
RUN rm -rf /usr/local/tomcat/webapps/*
# copy
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
# run the app on port 8080
EXPOSE 8080
# excute command catalina.sh run
CMD ["catalina.sh", "run"]
