# TP-DevOps

docker network create app-net

docker run -d --name db --network app-net -e MARIADB_ROOT_PASSWORD=secret -e MARIADB_DATABASE=test mariadb:11

docker build -t flask-db-app .

docker run --rm -p 5000:5000 --network app-net -e DB_HOST=db -e DB_USER=root -e DB_PASSWORD=secret -e DB_NAME=test flask-db-app

***Puis ouvrir http://localhost:5000***
