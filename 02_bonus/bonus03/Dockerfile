FROM debian

WORKDIR minecraft_server

RUN ["bash", "-c", "apt update && apt upgrade -y && apt install -y wget default-jre"]
RUN ["bash", "-c", "wget https://launcher.mojang.com/v1/objects/c5f6fb23c3876461d46ec380421e42b289789530/server.jar"]
RUN ["bash", "-c", "echo eula=true > eula.txt"]

EXPOSE 25565

ENTRYPOINT ["bash", "-c", "java -Xmx1024M -Xms1024M -jar server.jar nogui"]