FROM ubuntu
EXPOSE 3000/tcp
RUN apt update
RUN apt install wget --yes
RUN apt install sqlite --yes
RUN apt install git --yes
RUN adduser --system --group --disabled-password --shell /bin/bash --home /home/git --gecos 'Git Version Control' git
RUN wget -O /tmp/gitea https://dl.gitea.io/gitea/master/gitea-master-linux-amd64
RUN mv /tmp/gitea /usr/local/bin
RUN chmod +x /usr/local/bin/gitea
RUN mkdir -p /var/lib/gitea/custom
RUN mkdir -p /var/lib/gitea/data
RUN mkdir -p /var/lib/gitea/indexers
RUN mkdir -p /var/lib/gitea/public
RUN mkdir -p /var/lib/gitea/log
RUN chown git: /var/lib/gitea/data
RUN chown git: /var/lib/gitea/indexers
RUN chown git: /var/lib/gitea/log
RUN chmod 750 /var/lib/gitea/data
RUN chmod 750 /var/lib/gitea/indexers
RUN chmod 750 /var/lib/gitea/log
RUN mkdir /etc/gitea
RUN chown root:git /etc/gitea
RUN chmod 770 /etc/gitea
ENTRYPOINT ["gitea"]
