# DNS over HTTPS container

Quick run ready container from my DockerHub repository:
### With Cloudflare DNS
``` bash
docker run -it -d \
    --restart=always \
    -p 53:53/udp \
    -p 53:53 \
denzal/dns-over-https
```
### With Google DNS
``` bash
docker run -it -d \
    --restart=always \
    -p 53:53/udp \
    -p 53:53 \
denzal/dns-over-https
```
Build your own container from the source:
```bash
git clone git@github.com:denzalman/docker-dns-https.git
cd docker-dns-https
docker build --rm=true --force-rm=true -t denzal/dns-over-https .
docker push denzal/dns-over-https
```
If you run this container locally, change your host's DNS server IP to 127.0.0.1

To check if container works properly, run:
```bash
dig google.com @127.0.0.1
```
