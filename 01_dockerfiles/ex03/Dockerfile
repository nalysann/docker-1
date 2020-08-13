FROM debian

RUN apt update && apt upgrade -y && apt install -y wget openssh-server ca-certificates postfix
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && bash script.deb.sh
RUN apt install -y gitlab-ce

RUN mkdir -p /etc/gitlab/ssl
RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -subj "/C=RU/ST=Pepega/L=Pepega/O=Pepega/OU=Pepega/CN=pepega.com" -keyout /etc/gitlab/ssl/lab.key -out /etc/gitlab/ssl/lab.crt
RUN echo "nginx['ssl_certificate'] = \"/etc/gitlab/ssl/lab.crt\""  >> /etc/gitlab/gitlab.rb
RUN echo "nginx['ssl_certificate_key'] = \"/etc/gitlab/ssl/lab.key\"" >> /etc/gitlab/gitlab.rb
RUN echo "nginx['redirect_http_to_https'] = true" >> /etc/gitlab/gitlab.rb

EXPOSE 22 80 443

ENTRYPOINT echo "external_url \"https://$DOCKER_HOST_IP\"" >> /etc/gitlab/gitlab.rb && (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null