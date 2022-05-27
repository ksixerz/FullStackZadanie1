# FullStackZadanie1

#budowanie obrazu
docker build -f Dockerfile_Zadanie1 -t local/zadanie1:v1 . 
#usuwanie kontenera jeżeli juz istanial
docker rm zadanie1 -f
#tworzenie i uruchamianie kontenera
docker run -t -d --name "zadanie1" -p 1111:80/tcp local/zadanie1:v1
#podgląd logów przez konsole wewnętrzną
#docker exec -i -t zadanie1 /bin/sh
#tail -5  error.log 
#lub od razu jednym poleceniem
docker exec -i -t zadanie1 tail -5  /var/log/apache2/error.log

#3.d Wyswietlenie warstw
docker image inspect local/zadanie1:v1


docker login

docker buildx build -f Dockerfile_Zadanie1 -t ksixerz/zadanie1:v1 --platform linux/arm64,linux/amd64,linux/ppc64le,linux/arm/v7 --push .


Link dockerhub
https://hub.docker.com/repository/docker/ksixerz/zadanie1


