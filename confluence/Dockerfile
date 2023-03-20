#FROM cptactionhank/atlassian-confluence:latest
FROM atlassian/confluence-server:7.13.1-adoptopenjdk11

USER root

# 将代理破解包加入容器
COPY "atlassian-agent.jar" /opt/atlassian/confluence/
COPY "setenv.sh" /opt/atlassian/confluence/bin/setenv.sh
COPY "server.xml" /opt/atlassian/confluence/conf/server.xml
