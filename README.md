## Tomcat 9.0

### Build & Up Tomcat
```bash
docker-compose -f ./tomcat/docker-compose.yml up -d --build --force-recreate

docker exec -it mytomcat bash
docker exec -it mytomcat sh -c "ls /usr/local/tomcat/webapps"

docker restart mytomcat
docker port mytomcat
docker logs mytomcat

docker-compose logs mytomcat
```

### Build & Up Nginx
```bash
# docker run --name mynginx -d -p 80:80 -v /nginx/content:/usr/share/nginx/html:rw nginx
# -v /nginx/nginx.conf:/etc/nginx/nginx.conf
docker-compose -f ./nginx/docker-compose.yml up -d --build --force-recreate
docker exec -it mynginx /bin/bash
```

### Build & Up Jenkins
```bash
# docker run --name myjenkins -d -p 8080:8080 jenkinsci/blueocean \
# --env JAVA_OPTS="-Xmx8192m" --env JENKINS_OPTS="--handlerCountMax=300"

docker-compose -f ./jenkins/docker-compose.yml up -d --build --force-recreate

docker exec -it myjenkins bash
docker exec -it myjenkins sh -c "cat /var/jenkins_home/secrets/initialAdminPassword"
cat /root/dockers/jenkins/data/secrets/initialAdminPassword
```

#### Allow Port & List Port
```bash
# Centos - allow port 80, 443, 8080, ...
firewall-cmd --zone=public --add-port=80/tcp --permanent
firewall-cmd --reload

firewall-cmd --zone=public --add-port=8080/tcp --permanent
firewall-cmd --reload

lsof -i -P | grep http
lsof -i -P | grep postgres
lsof -i -P | grep docker

lsof -i -P | grep LISTEN
lsof -i -P -n | grep LISTEN

# Ubuntu - allow port 8080
sudo ufw status verbose
sudo ufw allow 8080/tcp


http://jenkin-domain/
http://jenkin-domain/cli/
http://jenkin-domain/env-vars.html/
```

## Jenkins Docker
https://technology.riotgames.com/news/putting-jenkins-docker-container
https://technology.riotgames.com/news/docker-jenkins-data-persists
https://dev.to/andresfmoya/install-jenkins-using-docker-compose-4cab