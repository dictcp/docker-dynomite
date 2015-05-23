Netflix Dynomite Docker image
==================================

Setup
-------

To setup Dynomite single node with redis backend:
- `docker run -d --name redisserver redis redis-server`
- `docker run -d --link redisserver:redisserver -p 8101:8101 -p 8102:8102 -p 22222:22222 dictcp/dynomite`

Alternatively, you can utilize the fig.xml if you checked out the source repository:
- `git clone https://github.com/dictcp/docker-dynomite`
- `cd docker-dynomite`
- `fig up`


Usage
-------

To access redis
- `redis-cli -p 8102`

To monitor stats
- `curl http://127.0.0.1:22222/ | python -mjson.tool`

TODO
-------

- build Dynomite with multiple nodes

