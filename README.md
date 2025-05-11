# Coredns
This is an example of a base DNS Server that routes the domain name 'homelab.in' and a wildcard subdomain

## Change the filler IP


```
sed -i 's/<my ip>/other/g' homelab.db
sed -i 's/<my ip>/other/g' docker-compose.yaml
```

## Run
Run coredns in docker
```
docker compose up -d
```

## Logs
```
docker logs coredns --follow
```
