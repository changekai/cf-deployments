# cf-deployments

## rabbitmq-deployment
```
bosh int rabbitmq-deployment.yml \
--vars-store cf-vars.yml \
-v environment=apps \
-v rabbitmq_haproxy_public_ip=<HAPROXY_PUBLIC_IP> \
-v domain=<DOMAIN>

bosh int rabbitmq-deployment.yml \
--vars-store cf-vars.yml \
-v environment=apps \
-v rabbitmq_haproxy_public_ip=124.9.14.27 \
-v domain=iii-cflab.com
```
