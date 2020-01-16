# code-alpine-with-https

[![Docker Repository on Quay](https://quay.io/repository/ks126/code-alpine-with-https/status "Docker Repository on Quay")](https://quay.io/repository/ks126/code-alpine-with-https)

```
docker create --name code-alpine -p 8080:8080 quay.io/ks126/code-alpine
docker cp code-alpine:/home/user/ca/server.crt code-alpine.crt
```

Next, add `code-alpine.crt` to your OS
