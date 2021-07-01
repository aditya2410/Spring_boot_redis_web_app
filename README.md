# Spring_boot_redis_web_app

This is web application which performs following basic tasks:
1) Register a user and collects following information:
  1.1) Email ID
  1.2) Name
  1.3) Age
  1.4) Occupation
2) Let a user search for his registered information using his email ID as key.


Web Famework used: Spring Boot (v2.4.3)
in-memory Data Cache technology used : Redis

Dependencies:
1) spring-boot-starter-web
2) spring-boot-starter-data-redis
3) spring-boot-starter-thymeleaf
4) Java Redis Client Library: Jedis (v3.3.0)


How to Run->
1) Download and start Redis Docker image :
CMD: docker pull redis
CMD: docker run --rm -p 4025:6379 -d --name redis-1 redis redis-server

2) Dowload docker image for this app :
CMD: docker pull aditya2410/adloidapp

3) Create Docker Network for communication between 2 dockers :
CMD: docker network create spring-redis-network

4)Add redis-1 to network :
CMD: docker network connect spring-redis-network redis-1

5)run the app and add it to spring-redis-network as wel :
CMD: docker run --net spring-redis-network -p 8080:8080 aditya2410/adloidapp

Note: make sure there is no other redis-server running on the host machine else HostName for redis server (running in redis-1) may change.
