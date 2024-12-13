# To build our containers



```
docker build -t backend-flask ./backend-flask/
docker build -t frontend-react-js ./frontend-react-js/

```

# To run our containers


```
docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask 
docker run -p 3000:3000 -d frontend-react-js
```



# Our just run the app via Docker-Compose 

```
docker-compose up -d
```


# To Create a table 

```
aws dynamodb create-table \
    --endpoint-url http://localhost:8000 \
    --table-name Music \
    --attribute-definitions \
        AttributeName=Artist,AttributeType=S \
        AttributeName=SongTitle,AttributeType=S \
    --key-schema AttributeName=Artist,KeyType=HASH AttributeName=SongTitle,KeyType=RANGE \
    --provisioned-throughput ReadCapacityUnits=1,WriteCapacityUnits=1 \
    --table-class STANDARD
```

# To add a record

```
aws dynamodb put-item \
    --endpoint-url http://localhost:8000 \
    --table-name Music \
    --item \
        '{"Artist": {"S": "No One You Know"}, "SongTitle": {"S": "Call Me Today"}, "AlbumTitle": {"S": "Somewhat Famous"}}' \
    --return-consumed-capacity TOTAL  
```    

# List tables
```
aws dynamodb list-tables --endpoint-url http://localhost:8000
```

# Get Records

```
aws dynamodb scan --table-name Music --query "Items" --endpoint-url http://localhost:8000
```

# Add conf to init section for GitPod

```
wget -qO - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" | sudo tee /etc/apt/sources.list.d/pgdg.list
sudo apt update
sudo apt install -y postgresql-client-13 libpq-dev
```


