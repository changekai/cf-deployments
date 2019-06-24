# rabbitmq-deployment

## application environment

```
bosh -e ENV -d apps-iothub-production deploy rabbitmq-deployment.yml \
  --vars-store ../apps-iothub-production-vars.yml \
  -v environment=apps \
  -v rabbitmq_server_private_ips=[10.10.16.100,10.10.32.100,10.10.48.100] \
  -v rabbitmq_haproxy_private_ip=10.10.16.90 \
  -v rabbitmq_haproxy_public_ip=RABBITMQ_HAPROXY_PUBLIC_IP \
  -v domain=DOMAIN
```

## operation environment

```
bosh -e ENV -d ops-iothub-production deploy rabbitmq-deployment.yml \
  --vars-store ../ops-iothub-production-vars.yml \
  -v environment=ops \
  -v rabbitmq_server_private_ips=[10.10.16.200,10.10.32.200,10.10.48.200] \
  -v rabbitmq_haproxy_private_ip=10.10.16.190 \
  -o operations/remove-haproxy-public-network.yml \
  -v domain=DOMAIN
```

## example command
```
bosh -e spacex -d apps-iothub-production deploy rabbitmq-deployment.yml \
  --vars-store apps-iothub-production-vars.yml    \
  -v environment=apps    \
  -v rabbitmq_server_private_ips=[10.10.16.100,10.10.32.100,10.10.48.100]    \
  -v rabbitmq_haproxy_private_ip=10.10.16.90    \
  -v rabbitmq_haproxy_public_ip=10.10.16.90    \
  -v domain=iii-cflab.com
```
