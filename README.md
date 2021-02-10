# camel-k-runtime-example-yaml

build:
```shell script
./mvnw package -Dnative
```

docker:
```shell script

docker run --rm -ti \
    -v $PWD/data:/etc/camel:Z \
    -e CAMEL_K_CONF=/etc/camel/application.properties \
    quay.io/lburgazzoli/camel-k-runtime-example-yaml:1.6.0-native
```

exec
```shell script

mvn exec:exec -Dnative
```

kamel
```shell script
kamel kit create --image=quay.io/lburgazzoli/camel-k-runtime-example-yaml:1.6.0-native camel-k-yaml-native
kamel run --dev --kit=camel-k-yaml-native -t jvm.enabled=false data/routes.yaml 
```