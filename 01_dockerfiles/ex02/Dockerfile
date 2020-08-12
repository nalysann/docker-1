FROM ruby

RUN ["bash", "-c", "curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -"]
RUN ["bash", "-c", "echo deb https://dl.yarnpkg.com/debian/ stable main | tee /etc/apt/sources.list.d/yarn.list"]
RUN ["bash", "-c", "apt update && apt upgrade -y && apt install -y yarn"]
RUN ["bash", "-c", "gem install rails"]

ONBUILD COPY pepega /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN ["bash", "-c", "yarn add jquery@3.5.1 bootstrap@3.4.1"]
ONBUILD RUN ["bash", "-c", "bundle update --bundler"]
ONBUILD RUN ["bash", "-c", "bundle install --without production"]
ONBUILD RUN ["bash", "-c", "rails db:migrate"]
ONBUILD RUN ["bash", "-c", "rails test"]
ONBUILD RUN ["bash", "-c", "rails db:seed"]