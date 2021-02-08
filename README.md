# camel-k-runtime-example-yaml

```shell script
./mvnw package -Dnative

docker run --rm -ti \
    -v $PWD/data:/etc/camel/sources:Z \
    -e CAMEL_K_ROUTES=file:/etc/camel/sources/routes.yaml \
    lburgazz/camel-k-runtime-example-yaml:1.6.0-native
```