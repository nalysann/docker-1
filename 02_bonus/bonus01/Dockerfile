FROM debian

RUN ["bash", "-c", "apt update && apt upgrade -y && apt install -y vim python3 python3-pip git"]
RUN ["bash", "-c", "python3 -m pip install --upgrade pip"]

ENTRYPOINT ["bash"]