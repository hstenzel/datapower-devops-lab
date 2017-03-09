FROM ibmcom/datapower:latest
ENV  DATAPOWER_ACCEPT_LICENSE=true \
     DATAPOWER_WORKER_THREADS=2 \
     DATAPOWER_INTERACTIVE=true
COPY config/ /drouter/config/
COPY local/ /drouter/local/
RUN  cd /root/secure/usrcerts \
       && ln -s /run/secrets/webgui_cert webgui-sscert.pem \
       && ln -s /run/secrets/webgui_key  webgui-privkey.pem \
       && mkdir foo \
       && cd foo \
       && ln -s /run/secrets/server_cert server.crt \
       && ln -s /run/secrets/server_key  server.key
EXPOSE 80 443 9090
