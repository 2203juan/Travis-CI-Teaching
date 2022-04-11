docker run --name my-postgres -e POSTGRES_PASSWORD=secret -p 5432:5432 -d postgres


docker run -p 80:8080  -e DB_HOST=$(docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-postgres) --name backend_cnt -d backend_img