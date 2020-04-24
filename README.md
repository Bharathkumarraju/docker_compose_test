# docker_compose_test
test the docker compose

#### docker-compose up
bharathdasaraju@MacBook-Pro composetest (master) $ docker-compose up

```
bharathdasaraju@MacBook-Pro composetest (master) $ docker-compose up
Building web
Step 1/9 : FROM python:3.7-alpine
 ---> 7fbc871584eb
Step 2/9 : WORKDIR /code
 ---> Running in 55b8211b14d1
Removing intermediate container 55b8211b14d1
 ---> 54af493d1887
Step 3/9 : ENV FLASK_APP app.py
 ---> Running in 511f0621bec8
Removing intermediate container 511f0621bec8
 ---> d2d8e8824417
Step 4/9 : ENV FLASK_RUN_HOST 0.0.0.0
 ---> Running in 6569e73c87ca
Removing intermediate container 6569e73c87ca
 ---> a3f7cf4b0624
Step 5/9 : RUN apk add --no-cache gcc musl-dev linux-headers
 ---> Running in 13e3630ad641
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.11/community/x86_64/APKINDEX.tar.gz
(1/12) Installing libgcc (9.2.0-r4)
(2/12) Installing libstdc++ (9.2.0-r4)
(3/12) Installing binutils (2.33.1-r0)
(4/12) Installing gmp (6.1.2-r1)
(5/12) Installing isl (0.18-r0)
(6/12) Installing libgomp (9.2.0-r4)
(7/12) Installing libatomic (9.2.0-r4)
(8/12) Installing mpfr4 (4.0.2-r1)
(9/12) Installing mpc1 (1.1.0-r1)
(10/12) Installing gcc (9.2.0-r4)
(11/12) Installing linux-headers (4.19.36-r0)
(12/12) Installing musl-dev (1.1.24-r2)
Executing busybox-1.31.1-r9.trigger
OK: 124 MiB in 46 packages
Removing intermediate container 13e3630ad641
 ---> c8c665c3a564
Step 6/9 : COPY requirements.txt requirements.txt
 ---> 09926efcf194
Step 7/9 : RUN pip install -r requirements.txt
 ---> Running in de2cfb8b81d6
Collecting flask
  Downloading Flask-1.1.2-py2.py3-none-any.whl (94 kB)
Collecting redis
  Downloading redis-3.4.1-py2.py3-none-any.whl (71 kB)
Collecting Jinja2>=2.10.1
  Downloading Jinja2-2.11.2-py2.py3-none-any.whl (125 kB)
Collecting Werkzeug>=0.15
  Downloading Werkzeug-1.0.1-py2.py3-none-any.whl (298 kB)
Collecting itsdangerous>=0.24
  Downloading itsdangerous-1.1.0-py2.py3-none-any.whl (16 kB)
Collecting click>=5.1
  Downloading click-7.1.1-py2.py3-none-any.whl (82 kB)
Collecting MarkupSafe>=0.23
  Downloading MarkupSafe-1.1.1.tar.gz (19 kB)
Building wheels for collected packages: MarkupSafe
  Building wheel for MarkupSafe (setup.py): started
  Building wheel for MarkupSafe (setup.py): finished with status 'done'
  Created wheel for MarkupSafe: filename=MarkupSafe-1.1.1-cp37-cp37m-linux_x86_64.whl size=32622 sha256=0222642edd5922390e4dbb85f9006e95549ee518445afa79485b7fdf5a4b0785
  Stored in directory: /root/.cache/pip/wheels/b9/d9/ae/63bf9056b0a22b13ade9f6b9e08187c1bb71c47ef21a8c9924
Successfully built MarkupSafe
Installing collected packages: MarkupSafe, Jinja2, Werkzeug, itsdangerous, click, flask, redis
Successfully installed Jinja2-2.11.2 MarkupSafe-1.1.1 Werkzeug-1.0.1 click-7.1.1 flask-1.1.2 itsdangerous-1.1.0 redis-3.4.1
Removing intermediate container de2cfb8b81d6
 ---> 9c9ce954e0f2
Step 8/9 : COPY . .
 ---> 7eeed048f3a6
Step 9/9 : CMD ["flask", "run"]
 ---> Running in 0960a72f631c
Removing intermediate container 0960a72f631c
 ---> 18eea3423c3f
Successfully built 18eea3423c3f
Successfully tagged composetest_web:latest
WARNING: Image for service web was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
Starting composetest_redis_1 ... 
Recreating composetest_web_1 ... error

Starting composetest_redis_1 ... done
22812297b593400b1dc6fcb81683da217f55b4f

ERROR: for web  no such image: sha256:1f066ec321b0bd2c46888171f22812297b593400b1dc6fcb81683da217f55b4f: No such image: sha256:1f066ec321b0bd2c46888171f22812297b593400b1dc6fcb81683da217f55b4f
ERROR: The image for the service you're trying to recreate has been removed. If you continue, volume data could be lost. Consider backing up your data before continuing.

Continue with the new image? [yN]y
composetest_redis_1 is up-to-date
Recreating 738505a6a67b_composetest_web_1 ... done
Attaching to composetest_redis_1, composetest_web_1
redis_1  | 1:C 24 Apr 2020 02:51:11.235 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
redis_1  | 1:C 24 Apr 2020 02:51:11.235 # Redis version=5.0.9, bits=64, commit=00000000, modified=0, pid=1, just started
redis_1  | 1:C 24 Apr 2020 02:51:11.235 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
redis_1  | 1:M 24 Apr 2020 02:51:11.236 * Running mode=standalone, port=6379.
redis_1  | 1:M 24 Apr 2020 02:51:11.236 # WARNING: The TCP backlog setting of 511 cannot be enforced because /proc/sys/net/core/somaxconn is set to the lower value of 128.
redis_1  | 1:M 24 Apr 2020 02:51:11.236 # Server initialized
redis_1  | 1:M 24 Apr 2020 02:51:11.236 # WARNING you have Transparent Huge Pages (THP) support enabled in your kernel. This will create latency and memory usage issues with Redis. To fix this issue run the command 'echo never > /sys/kernel/mm/transparent_hugepage/enabled' as root, and add it to your /etc/rc.local in order to retain the setting after a reboot. Redis must be restarted after THP is disabled.
redis_1  | 1:M 24 Apr 2020 02:51:11.237 * Ready to accept connections
redis_1  | 1:signal-handler (1587696885) Received SIGTERM scheduling shutdown...
redis_1  | 1:M 24 Apr 2020 02:54:45.172 # User requested shutdown...
redis_1  | 1:M 24 Apr 2020 02:54:45.173 * Saving the final RDB snapshot before exiting.
redis_1  | 1:M 24 Apr 2020 02:54:45.176 * DB saved on disk
redis_1  | 1:M 24 Apr 2020 02:54:45.176 # Redis is now ready to exit, bye bye...
redis_1  | 1:C 24 Apr 2020 02:55:33.933 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
redis_1  | 1:C 24 Apr 2020 02:55:33.936 # Redis version=5.0.9, bits=64, commit=00000000, modified=0, pid=1, just started
redis_1  | 1:C 24 Apr 2020 02:55:33.936 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
redis_1  | 1:M 24 Apr 2020 02:55:33.938 * Running mode=standalone, port=6379.
redis_1  | 1:M 24 Apr 2020 02:55:33.938 # WARNING: The TCP backlog setting of 511 cannot be enforced because /proc/sys/net/core/somaxconn is set to the lower value of 128.
redis_1  | 1:M 24 Apr 2020 02:55:33.938 # Server initialized
redis_1  | 1:M 24 Apr 2020 02:55:33.938 # WARNING you have Transparent Huge Pages (THP) support enabled in your kernel. This will create latency and memory usage issues with Redis. To fix this issue run the command 'echo never > /sys/kernel/mm/transparent_hugepage/enabled' as root, and add it to your /etc/rc.local in order to retain the setting after a reboot. Redis must be restarted after THP is disabled.
redis_1  | 1:M 24 Apr 2020 02:55:33.939 * DB loaded from disk: 0.000 seconds
redis_1  | 1:M 24 Apr 2020 02:55:33.939 * Ready to accept connections
redis_1  | 1:signal-handler (1587696947) Received SIGTERM scheduling shutdown...
redis_1  | 1:M 24 Apr 2020 02:55:47.221 # User requested shutdown...
redis_1  | 1:M 24 Apr 2020 02:55:47.221 * Saving the final RDB snapshot before exiting.
redis_1  | 1:M 24 Apr 2020 02:55:47.226 * DB saved on disk
redis_1  | 1:M 24 Apr 2020 02:55:47.226 # Redis is now ready to exit, bye bye...
redis_1  | 1:C 24 Apr 2020 02:57:06.142 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
redis_1  | 1:C 24 Apr 2020 02:57:06.142 # Redis version=5.0.9, bits=64, commit=00000000, modified=0, pid=1, just started
redis_1  | 1:C 24 Apr 2020 02:57:06.142 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
redis_1  | 1:M 24 Apr 2020 02:57:06.144 * Running mode=standalone, port=6379.
redis_1  | 1:M 24 Apr 2020 02:57:06.144 # WARNING: The TCP backlog setting of 511 cannot be enforced because /proc/sys/net/core/somaxconn is set to the lower value of 128.
redis_1  | 1:M 24 Apr 2020 02:57:06.144 # Server initialized
redis_1  | 1:M 24 Apr 2020 02:57:06.144 # WARNING you have Transparent Huge Pages (THP) support enabled in your kernel. This will create latency and memory usage issues with Redis. To fix this issue run the command 'echo never > /sys/kernel/mm/transparent_hugepage/enabled' as root, and add it to your /etc/rc.local in order to retain the setting after a reboot. Redis must be restarted after THP is disabled.
redis_1  | 1:M 24 Apr 2020 02:57:06.145 * DB loaded from disk: 0.000 seconds
redis_1  | 1:M 24 Apr 2020 02:57:06.145 * Ready to accept connections
web_1    |  * Serving Flask app "app.py"
web_1    |  * Environment: production
web_1    |    WARNING: This is a development server. Do not use it in a production deployment.
web_1    |    Use a production WSGI server instead.
web_1    |  * Debug mode: off
web_1    |  * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:24] "GET / HTTP/1.1" 200 -
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:24] "GET /favicon.ico HTTP/1.1" 404 -
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:28] "GET / HTTP/1.1" 200 -
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:28] "GET / HTTP/1.1" 200 -
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:28] "GET / HTTP/1.1" 200 -
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:28] "GET / HTTP/1.1" 200 -
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:29] "GET / HTTP/1.1" 200 -
web_1    | 172.21.0.1 - - [24/Apr/2020 02:57:29] "GET / HTTP/1.1" 200 -

```
