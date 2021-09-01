FROM openjdk:8-jdk-alpine
RUN apk update && apk add bash
RUN apk add git
RUN apk add maven
RUN git clone https://github.com/ismaelvarez/kurento.git
RUN cd kurento && \
	git submodule init && \
	git submodule update && \
	mvn clean compile install package -DskipTests

ENTRYPOINT ["java","-jar","/kurento/kurento-application-server/target/kurentoserver-0.0.1-SNAPSHOT-exec.jar"]
