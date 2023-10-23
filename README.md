# golang-simplebank  

spin up a postgres docker image:  
docker run --name postgres12 -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=secret -d postgres:12-alpine  
docker exec -it postgres12 psql -U root  
docker logs postgres12  

db diagram ref link:  https://dbdiagram.io/d/golangsimplebank-65363308ffbf5169f03e6a3b  
