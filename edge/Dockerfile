FROM ubuntu:18.04

RUN apt-get update -qq && apt-get install -qqy apt-transport-https ca-certificates curl gnupg systemd net-tools

RUN curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list > /etc/apt/sources.list.d/microsoft-prod.list
RUN curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > /etc/apt/trusted.gpg.d/microsoft.gpg

# RUN curl -sSL https://raw.githubusercontent.com/moby/moby/master/contrib/check-config.sh -o check-config.sh
# RUN chmod +x check-config.sh

RUN apt-get update -qq && apt-get install -qqy moby-engine moby-cli
RUN apt-get install -y --no-install-recommends iotedge
RUN rm -rf /var/lib/apt/lists/*

COPY start-edge-runtime.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/start-edge-runtime.sh

VOLUME /var/lib/docker

EXPOSE 2375
EXPOSE 15580
EXPOSE 15581

ENTRYPOINT ["bash", "start-edge-runtime.sh"]

CMD []