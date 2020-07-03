FROM tomcat:9.0

RUN echo $CATALINA_HOME

ADD ./conf/tomcat-users.xml /usr/local/tomcat/conf/
ADD ./conf/context.xml /usr/local/tomcat/webapps.dist/manager/META-INF/
ADD ./conf/context.xml /usr/local/tomcat/webapps.dist/host-manager/META-INF

# RUN cp -avT $CATALINA_HOME/webapps.dist/manager $CATALINA_HOME/webapps/manager
# RUN cp -avT $CATALINA_HOME/webapps.dist/ROOT $CATALINA_HOME/webapps/ROOT
RUN cp -r $CATALINA_HOME/webapps.dist/* $CATALINA_HOME/webapps/

# ENV spring.profiles.active=prd
# ENV CATALINA_OPTS="-Dkey=value" 

# COPY ./entrypoint.sh /usr/bin/
# RUN chmod +x /usr/bin/entrypoint.sh
# ENTRYPOINT ["/usr/bin/entrypoint.sh"]
# RUN mv /usr/local/tomcat/webapps /usr/local/tomcat/webapps2
# RUN mv /usr/local/tomcat/webapps.dist /usr/local/tomcat/webapps

EXPOSE 8080

CMD ["catalina.sh", "run"]