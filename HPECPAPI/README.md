# HPECPAPI notes

```bash
curl -k -i -s --request POST "http://ez53-gateway.hpeilab.com:8080/api/v2/session" \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
"name": "username",
"password": "password",
"tenant_name": "test-tenant"
}'

#
HTTP/1.1 201 Created
Access-Control-Allow-Origin: *
Content-Length: 13
Content-Type: text/plain
Date: Fri, 30 Apr 2021 13:18:38 GMT
Location: /api/v2/session/thisisthesessionid
Server: HPE Ezmeral Container Platform 5.3

201 Created
```
```bash

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
