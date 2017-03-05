FROM ibmcom/datapower:latest
ENV  DATAPOWER_ACCEPT_LICENSE=true \
     DATAPOWER_WORKER_THREADS=2 \
     DATAPOWER_INTERACTIVE=true
COPY config/ /drouter/config/
COPY local/ /drouter/local/
RUN  cd /root/secure/ && rm -rf usrcerts && ln -s /secret/ usrcerts
EXPOSE 80 443 9090
