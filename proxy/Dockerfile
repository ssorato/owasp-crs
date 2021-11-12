FROM owasp/modsecurity-crs:3.3.2-nginx

COPY nginx_default.conf /etc/nginx/conf.d/default.conf
COPY 40x.html /usr/share/nginx/html/40x.html
COPY 50x.html /usr/share/nginx/html/50x.html
COPY modsecurity-override.conf /etc/modsecurity.d/modsecurity-override.conf
COPY crs-setup.conf /etc/modsecurity.d/owasp-crs/crs-setup.conf
RUN mkdir -p /var/log/modsecurity/audit/ && \
    ln -s /dev/stdout /var/log/nginx/secdebug.log && \
    chown -R nginx /tmp/modsecurity

