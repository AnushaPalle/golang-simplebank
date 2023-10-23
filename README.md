# golang-simplebank  

spin up a postgres docker image:  
docker run --name postgres12 -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=secret -d postgres:12-alpine  
docker exec -it postgres12 psql -U root  
docker logs postgres12  

docker exec -it postgres12 /bin/sh  
createdb --username=root --owner=root golang_simplebank  
psql golang_simplebank  
dropdb golang_simplebank  
exit -> to get out of shell 

or  

docker exec -it postgres12 createdb --username=root --owner=root golang_simplebank  
docker exec -it postgres12 psql -U root golang_simplebank  

db diagram ref link:  https://dbdiagram.io/d/golangsimplebank-65363308ffbf5169f03e6a3b  

writing and running db migrations:  
install tool: brew install golang-migrate  
migrate create -ext sql -dir db/migration -seq init_schema  

running migration:  
migrate -path db/migration -database "postgresql://root:secret@localhost:5432/golang_simplebank?sslmode=disable" -verbose up  
