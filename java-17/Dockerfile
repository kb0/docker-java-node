FROM openjdk:17-jdk-buster
MAINTAINER Kirill Bychkov <kb@na.ru>

RUN apt-get update -qq && apt-get install -qq --no-install-recommends \
  bash curl gnupg2

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && apt-get update -qq && apt-get install -qq --no-install-recommends \
      nodejs yarn \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
