FROM alpine:3.3
USER root

ENV MAVEN_VERSION 3.3.9
ENV MAVEN_URL http://mymaven.url/$MAVEN_VERSION-bin.tar.gz

RUN -p /opt/maven /opt/maven/ref \
&& curl -fSsl ${MAVEN_URL} -o maven.tar \
&& tar -xzf maven.tar -C /opt/maven \
&&  mvn --version

ENV MAVEN_HOME /opt/maven/
ENV MAVEN_CONFIG "/opt/maven/.M2"

ENV SONAR_VERSION 2.8
ENV SONAR_SHA 0bbd64d7b63ea64c4757c37fa853386bae87d4fc
ENV SONAR_URL http://mysonar.repo/sonar-scanner-${SONAR_VERSION}.zip

ENV SONAR_RUNNER_HOME /opt/sonar/sonar-scanner

RUN curl -fSsl ${SONAR_URL} -o sonar-scanner.zip \
&& echo ${SONAR_SHA} sonar-scanner.zip | sha1sum -c \
&& unzip sonar-scanner.zip -d /opt/sonar \
&& sonar-runner --version



