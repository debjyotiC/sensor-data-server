# Sensor data server
A remote data server using RESTful API running on docker.

# Docker build technique
1. 


# cURL query to test RESTful API
1. Push data to data server
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"key": "aa", "data": 25.5}' http://localhost:5000/update
    ```
2. Get data from the server
    ```bash
    curl -X GET "http://localhost:5000/feeds?key=aa"
    ```
   
# Attaching MongoDB to the docker container
1. Pull official mongodb image
    ```bash
    docker pull mongo
    ```
2. Run mongo image and call it mongodb    
   ```bash
    docker run -d --name mongodb -p 27017:27017 mongo
    ```
3. Build server image
   ```bash
    docker build -t data-server . 
    ```
4. Run the server image and attach mongodb 
   ```bash
    docker run -d --name data-server -p 5000:5000 --link mongodb data-server
    ```
