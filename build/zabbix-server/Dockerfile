FROM maborak/zabbix6-base

RUN addgroup --system --gid 1995  --quiet zabbix && \
    adduser --quiet --uid 1997 --system --ingroup zabbix --home /var/lib/zabbix --no-create-home zabbix
#USER 1997
