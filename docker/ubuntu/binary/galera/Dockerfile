FROM %%KOLLA_NAMESPACE%%/%%KOLLA_PREFIX%%base:%%KOLLA_TAG%%
MAINTAINER Kolla Project (https://launchpad.net/kolla)

RUN apt-key adv --recv-keys --keyserver \
        hkp://keyserver.ubuntu.com:80 0xcbcb082a1bb943db \
    && add-apt-repository \
        'deb http://ams2.mirrors.digitalocean.com/mariadb/repo/5.5/ubuntu \
        trusty main' \
    && apt-get update \
    && apt-get install -y \
        mariadb-galera-server \
        galera \
    && apt-get clean

COPY config-galera.sh /opt/kolla/config-galera.sh
COPY start.sh /start.sh

CMD ["/start.sh"]
