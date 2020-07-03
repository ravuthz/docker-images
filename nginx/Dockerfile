FROM nginx

# RUN rm /etc/nginx/nginx.conf /etc/nginx/conf.d/default.conf
COPY content /usr/share/nginx/html
# COPY conf /etc/nginx

VOLUME /var/log/nginx/log
VOLUME /usr/share/nginx/html
VOLUME /etc/nginx/

# docker build -t mynginx_image .
# docker run --name mynginx -p 8080:80 -d mynginx_image


# docker-compose up --build --force-recreate
# docker run -it --rm -p 8080:8080 tomcat:9.0
# docker run --name mytomcat -p 8080:8080 -v $PWD/test:/usr/local/tomcat/webapps/test -d tomcat

# docker run --name mytomcat -p 8080:8080 -d tomcat