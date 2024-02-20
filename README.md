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