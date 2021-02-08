# camel-k-runtime-example-yaml

```shell script
./mvnw package -Dnative

docker run --rm -ti \
    -v $PWD/data:/etc/camel/sources:Z \
    -e CAMEL_K_ROUTES=file:/etc/camel/sources/routes.yaml \
    quay.io/lburgazzoli/camel-k-runtime-example-yaml:1.6.0-native
```

```shell script
kamel kit create --image=quay.io/lburgazzoli/camel-k-runtime-example-yaml:1.6.0-native camel-k-yaml-native
kamel run --dev --kit=camel-k-yaml-native -t jvm.enabled=false data/routes.yaml 
```