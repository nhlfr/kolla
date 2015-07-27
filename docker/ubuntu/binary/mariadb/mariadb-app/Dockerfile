FROM %%KOLLA_NAMESPACE%%/%%KOLLA_PREFIX%%base:%%KOLLA_TAG%%
MAINTAINER Kolla Project (https://launchpad.net/kolla)

RUN apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xcbcb082a1bb943db \
    && add-apt-repository 'deb http://sfo1.mirrors.digitalocean.com/mariadb/repo/5.5/ubuntu trusty main' \
    && apt-get install -y --no-install-recommends \
        hostname \
        mariadb-server \
        python-mysqldb \
    && apt-get clean

COPY config-mysql.sh mysql-entrypoint.sh /opt/kolla/

ENTRYPOINT ["/opt/kolla/mysql-entrypoint.sh" ]
CMD ["mysqld_safe"]
