FROM            ubuntu:18.04

RUN             apt-get update && \
                apt-get upgrade -y && \
                apt-get install -y wget ca-certificates openssh-server postfix

RUN             wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod 777 script.deb.sh && ./script.deb.sh && apt-get install -y tzdata gitlab-ce
 
EXPOSE          443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && sleep 2 && gitlab-ctl reconfigure && tail -f /dev/null

#docker run -dit -p 8443:443 -p 8022:22 -p 8080:80 --privileged ex03l
