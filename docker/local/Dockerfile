#
# MockServer Dockerfile
#
# https://github.com/mock-server/mockserver
# http://www.mock-server.com
#

# runtime image: golden JDK 17 (Chainguard, distroless, uid 65532)
FROM 694713800774.dkr.ecr.us-east-2.amazonaws.com/golden/jdk:openjdk-17

# maintainer details
MAINTAINER James Bloom "jamesdbloom@gmail.com"

# expose ports.
EXPOSE 1080

# copy in jar
COPY mockserver-netty-jar-with-dependencies.jar /

# don't run MockServer as root
USER 65532

ENTRYPOINT ["java", "-Dfile.encoding=UTF-8", "-cp", "/mockserver-netty-jar-with-dependencies.jar:/libs/*", "-Dmockserver.propertyFile=/config/mockserver.properties", "org.mockserver.cli.Main"]

CMD ["-serverPort", "1080"]
