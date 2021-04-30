# HPECPAPI notes

```
curl -k -i -s --request POST "http://ez53-gateway.hpeilab.com:8080/api/v2/session" \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
"name": "username",
"password": "password",
"tenant_name": "test-tenant"
}'
```

## code
```bash
curl -k -s --request GET "http://ez53-gateway.hpeilab.com:8080/api/v2/k8skubeconfig" \
--header "X-BDS-SESSION: $(curl -k -i -s --request POST "http://ez53-gateway.hpeilab.com:8080/api/v2/session" \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
"name": "change-your-user-name",
"password": "change-your-user-password",
"tenant_name": "change-the-tenant-you-want"
}' | grep Location | awk '{print $2}' | tr -d '\r')" \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' > ./kubeconfig

export KUBECONFIG="./kubeconfig"

kubectl get pods
```
