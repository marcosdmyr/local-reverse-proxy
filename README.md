# local-reverse-proxy

>  [traefik](https://github.com/containous/traefik) and [mkcert](https://github.com/FiloSottile/mkcert) based reverse proxy

#### How to use?
* clone this repo
* create your certificates and update certificates.toml if neccesary
* create docker network and do up!
* add necessary labels on your existing running containers

`$ git clone git@github.com:marcosdmyr/local-reverse-proxy.git`

`$ mkcert -cert-file certs/traefik.localhost.cert -key-file certs/traefik.localhost.key "traefik.localhost" "*.localhost" localhost 127.0.0.1 ::1`

`$ docker-compose up -d`

Open https://traefik.localhost with your web browser!

#### Requirements
* docker
* docker-compose
* mkcert (optional)
* ensure localhost subdomains resolves to 127.0.0.1

#### TODO
- Use [traefik go templating](https://docs.traefik.io/providers/file/#go-templating) or [jwilder/docker-gen](https://github.com/jwilder/docker-gen) to write /etc/traefik/certificates.toml based on labels
- Generate service certificates on the fly based on labels
- Add dns to make it work on firefox
