FROM debian

RUN ["bash", "-c", "apt update && apt upgrade -y && apt install -y wget bzip2"]

WORKDIR /root/teamspeak

RUN ["bash", "-c", "wget https://files.teamspeak-services.com/releases/server/3.12.1/teamspeak3-server_linux_amd64-3.12.1.tar.bz2"]
RUN ["bash", "-c", "tar -xf teamspeak3-server_linux_amd64-3.12.1.tar.bz2"]

EXPOSE 9987/udp 30033

ENV TS3SERVER_LICENSE=accept

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT ["bash", "ts3server_minimal_runscript.sh"]