FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install


# ------Second Stage-------- #

FROM openjdk:11.0.10-jre
WORKDIR /app
COPY --from=build /app/targate/zuul-0.0.1-SNAPSHOT.jar /app/
EXPOSE 9999
CMD [ "java" , "-jar" , "zuul-0.0.1-SNAPSHOT.jar.jar" ]
