FROM tomcat:8-jre8

MAINTAINER <registry@oneasp.com>

ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH

RUN mkdir -p /oneasp/OneRASP

ADD OneRASP /oneasp/OneRASP

RUN sed -i '249 a CATALINA_OPTS="-javaagent:/oneasp/OneRASP/lib/RaspAgent.jar $CATALINA_OPTS"' $CATALINA_HOME/bin/catalina.sh

VOLUME /usr/local/tomcat/webapps

CMD ["sh","/oneasp/OneRASP/docker/docker-run.sh"]
