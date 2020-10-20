# docker_multiple_local_container

Docker use two local containers: Node and Redis
Description: track number of visits of web page.

![image](https://user-images.githubusercontent.com/46542567/96537974-7b9fd000-1265-11eb-8a1e-2eaf650a84ce.png)

Situation 1: put into "same" container
![image](https://user-images.githubusercontent.com/46542567/96538034-97a37180-1265-11eb-9921-2e5648caf52f.png)

Problem:
Everytime users load the docker container, will have individual copy of Redis. It will cause the happening like this:
![image](https://user-images.githubusercontent.com/46542567/96538111-c4f01f80-1265-11eb-8a9e-341e9455c53a.png)

Because everyone has his own redis, the cache will count different number of visits. It is incorrect.


Revise: put into two different container
![image](https://user-images.githubusercontent.com/46542567/96538170-ebae5600-1265-11eb-925e-42df2862b899.png)

There are two ways to connecting multiple containers:
1. use Docker CLI : handy, complicated
2. Use Docker Compose : relatively simple. It actually works like Docker CLI but quickly and easier.

![image](https://user-images.githubusercontent.com/46542567/96538185-f4069100-1265-11eb-9dc5-bd853f54d923.png)

![image](https://user-images.githubusercontent.com/46542567/96538269-3203b500-1266-11eb-9725-912cf0404abc.png)
![image](https://user-images.githubusercontent.com/46542567/96538297-3def7700-1266-11eb-8cdd-240c7ac8ed64.png)

This is the structure of this docker app: Use Docker Compose can connect two separate containers.
![image](https://user-images.githubusercontent.com/46542567/96538310-45168500-1266-11eb-9860-d43b91870e02.png)

Here is the way to run
![image](https://user-images.githubusercontent.com/46542567/96538410-77c07d80-1266-11eb-960b-dbbdfb2af9b5.png)

docker build . <br>
docker run redis <br>
docker-compose up --build <br>
docker-compose up <br>

