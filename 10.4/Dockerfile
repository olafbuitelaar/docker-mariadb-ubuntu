# vim:set ft=dockerfile:
FROM mariadb:10.4

ARG PKGS="ansible python-apt aptitude"
ARG ENABLE_CRACKLIB=1
ARG ENABLE_ROCKSDB=1
COPY install.yml packages.yml /

RUN \
        apt-get update && \
        apt-get -y install $PKGS && \
        ansible-playbook -D /install.yml -e enable_cracklib=$ENABLE_CRACKLIB -e enable_rocksdb=$ENABLE_ROCKSDB && \
        apt-get -y purge $PKGS && \
        apt-get -y --purge autoremove && \
        apt-get -y clean && \
        rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /*.yml
