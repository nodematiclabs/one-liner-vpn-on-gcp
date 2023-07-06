# Run Your Own VPN (One-Liner) on Google Cloud

```bash
docker run -d \
  --name=wireguard \
  --cap-add=NET_ADMIN \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Etc/UTC \
  -e PEERS=1 \
  -p 51820:51820/udp \
  -v /var/config:/config \
  --sysctl="net.ipv4.conf.all.src_valid_mark=1" \
  --restart unless-stopped \
  lscr.io/linuxserver/wireguard:latest
```
