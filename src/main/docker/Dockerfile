#FROM ${image-registry-host}:${image-registry-port}/myproject/openjdk:8-jdk-alpine
FROM openjdk:8

ADD %project.artifactId%-%project.version%.jar app.jar

#RUN adduser -S 1000

VOLUME /data/files

#USER 1000

ENV JAVA_OPTS="-XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -Xms512m -Xmx512m"

ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]