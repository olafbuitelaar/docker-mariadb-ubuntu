# vim:set ft=dockerfile:
FROM mariadb:10.1

ARG PKGS="ansible python-apt aptitude"
COPY install.yml packages.yml /

RUN \
        apt-get update && \
        apt-get -y install $PKGS && \
        ansible-playbook -D /install.yml && \
        apt-get -y purge $PKGS && \
        apt-get -y --purge autoremove && \
        apt-get -y clean && \
        rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /*.yml
