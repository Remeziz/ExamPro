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



