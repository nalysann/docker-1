FROM cdev

RUN ["bash", "-c", "apt update && apt upgrade -y && apt install -y wget"]
RUN ["bash", "-c", "wget https://raw.githubusercontent.com/mevdschee/2048.c/master/2048.c"]
RUN ["bash", "-c", "gcc -o 2048 2048.c"]

ENTRYPOINT ["bash", "-c", "./2048"]