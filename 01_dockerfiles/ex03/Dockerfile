FROM debian

RUN ["bash", "-c", "apt update && apt upgrade -y && apt install -y wget openssh-server ca-certificates postfix"]
RUN ["bash", "-c", "wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh"]
RUN ["bash", "-c", "bash script.deb.sh"]
RUN ["bash", "-c", "apt install -y gitlab-ce"]

EXPOSE 22 80 443

ENTRYPOINT ["bash", "-c", "(/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null"]