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

## Update servier to point to custom DNS Server
### Linux Update /etc/resolv.conf
...
nameserver <dns ip>
nameserver ...
...

### Windows point to Custom DNS Server
Set-DnsClientServerAddress -InterfaceAlias Wi-Fi -ServerAddresses ("<dns ip>", "...")

## Undo update to use local DNS Server
### Linux 
Remove added nameserver line in /etc/resolv.conf

### Windows
Set-DnsClientServerAddress -InterfaceAlias Wi-Fi -ServerAddresses ("...")
