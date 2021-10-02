### Generate SSL
* https://github.com/FiloSottile/mkcert
```
mkcert -cert-file ./docker/certs/default.crt -key-file ./docker/certs/default.key local-dev.noir.ai

docker run --rm -v $PWD/out:/out -e HOST=local-dev.noir.ai -e IP=172.0.0.1 tkuni83/self-sign-cert
```
