# Kerberos as a Container
Notes on docker-kdc

## Requirements
##### Server
docker


##### Client


## Build
```bash
docker build --no-cache -t $DOCKERIMAGE .
rm -f Dockerfile
rm -f krb5.conf
```

## Init
To start the container:
```bash
docker run -d -h $KDC_HOST_NAME \
  -p $KDC_PORT:88 \
  -p $KDC_PORT:88/udp \
  --name=$KDC_HOST_NAME \
  $DOCKERIMAGE
```

##### Template
```bash
sed -e "s/HOST_NAME/$KDC_HOST:$KDC_PORT/g"  \
  -e "s/DOMAIN_NAME/$KDC_DOMAIN_NAME/g" \
  -e "s/REALM_NAME/$KDC_REALM_NAME/g" \
  "$TEMPLATE_DIR/krb5.conf" >krb5.conf
```


```bash
export KRB5_CONFIG=$(pwd)/krb5.conf"
export KRB5_KTNAME=$(pwd)/krb5.keytab"
```

## Stop
Be sure to stop gracefully, redirect output to something other
than `/dev/null` if you want the log.

```bash
docker stop $KDC_HOST_NAME &> /dev/null
docker rm $KDC_HOST_NAME &> /dev/null
rm -f krb5.conf
rm -f krb5.keytab
```

###### Build Image
The following is ripped from

```bash
local RENDER_PRINCIPAL="RUN /bin/echo -e '\n\n\n\n\nPASSWORD\nPASSWORD\n" |kadmin -l add PRINCIPAL"
local EXPORT_KEYTAB="RUN kadmin -l ext_keytab -k /etc/docker-kdc/krb5.keytab"
```


