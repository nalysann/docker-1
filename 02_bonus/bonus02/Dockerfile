FROM debian

ENV GOROOT /usr/local/go
ENV GOPATH $HOME/projects
ENV PATH $PATH:$GOROOT/bin:$GOPATH/bin

RUN ["bash", "-c", "apt update && apt upgrade -y && apt install -y wget vim git"]
RUN ["bash", "-c", "wget https://golang.org/dl/go1.15.linux-amd64.tar.gz"]
RUN ["bash", "-c", "tar -xvf go1.15.linux-amd64.tar.gz && rm -f go1.15.linux-amd64.tar.gz && mv go /usr/local"]

ENTRYPOINT ["bash"]