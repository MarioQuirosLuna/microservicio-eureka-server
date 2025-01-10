# CREAR PACKAGE

## Genera el package en target

```bash
$ ./mvnw clean package
```

# EJECUTAR CON DOCKER

## Crear build

```docker
sudo docker build -t eureka-server:v1 .
```

## Ver imagenes creadas

```docker
sudo docker images
```

## Crear una red para que los contenedores se comuniquen

SOLO SI NO HA SIDO CREADA PREVIAMENTE

```docker
sudo docker network create springcloud
```

## Levantar contenedor en puerto externo:virtual / nombre maquina / red / imagen apartir de la que se crea

```docker
sudo docker run -p 8761:8761 --name eureka-server --network springcloud eureka-server:v1
```

Si el puerto fuera dinamico se utiliza -P

```docker
sudo docker run -P ...
```