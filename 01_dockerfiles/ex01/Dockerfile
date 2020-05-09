FROM            debian
RUN             apt-get update -y && \
                apt-get upgrade -y && \
                apt-get install -y wget && \
                apt-get install -y bzip2 && \
                wget https://files.teamspeak-services.com/releases/server/3.11.0/teamspeak3-server_linux_amd64-3.11.0.tar.bz2 && \
                tar -xvf teamspeak3-server_linux_amd64-3.11.0.tar.bz2 && \
                rm -rf teamspeak3-server_linux_amd64-3.11.0.tar.bz2 && \
                cd teamspeak3-server_linux_amd64 && \
                touch .ts3server_license_accepted
EXPOSE          9987/udp
EXPOSE          10011
EXPOSE          30033
CMD             ["./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh", "start"]