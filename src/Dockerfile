FROM quay.io/ks126/code-alpine
USER user
WORKDIR /home/user
RUN mkdir ca \
&& cd ca \
&& chmod 700 . \
&& doas apk add --no-cache openssl \
&& openssl genrsa 2048 > server.key \
&& openssl req -new -key server.key -subj "/C=AU/ST=Some-State/L=/O=Internet Widgets Pty Ltd/OU=/CN=" > server.csr \
&& openssl x509 -days 365000 -req -signkey server.key < server.csr > server.crt
EXPOSE 8080
ENTRYPOINT [ "code-server", "--cert", "/home/user/ca/server.crt", "--cert-key", "/home/user/ca/server.key" ]