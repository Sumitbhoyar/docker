FROM alpine

# Install JDK
RUN apk --update add openjdk7

# Install maven
RUN wget http://redrockdigimark.com/apachemirror/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
RUN tar -zxvf apache-maven-3.3.9-bin.tar.gz
RUN rm apache-maven-3.3.9-bin.tar.gz
RUN mv apache-maven-3.3.9 /usr/lib/mvn

ENV JAVA_HOME /usr/lib/jvm/java-1.7-openjdk
ENV JAVA=$JAVA_HOME/bin
ENV M2_HOME=/usr/lib/mvn
ENV M2=$M2_HOME/bin
ENV PATH $PATH:$JAVA_HOME:$JAVA:$M2_HOME:$M2

WORKDIR /code

# Prepare by downloading dependencies
ADD pom.xml /code/pom.xml
RUN ls pom.xml
#RUN mvn dependency:resolve
#RUN mvn verify

# Adding source, compile and package into a fat jar
ADD src /code/src
#RUN mvn package
RUN wait
#EXPOSE 4567
#CMD ["/usr/bin/java", "-jar", "target/sparkexample-jar-with-dependencies.jar"]
CMD echo 1111
