FROM maborak/zabbix6-base-git AS base

FROM trafex/php-nginx
WORKDIR /var/www/html
COPY --from=base /var/lib/zabbix_ui/ ./

