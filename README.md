# BigBlueButton Docker

It's fork of https://github.com/bigbluebutton/docker

Main goal is make it work with hostname and get possibility to chose external ip
Secondary goal - integrate letsencrypt 

These are scripts to build a Docker that runs BigBlueButton with both the Flash and HTML5 client.  To build the Docker container, run the command

~~~
docker build -t bigbluebutton .
~~~

Here we called the BigBlueButton container `bigbluebutton`. To run BigBlueButton in Docker, run the command

~~~
docker run --rm -p 443:443/tcp -p 80:80/tcp -p 1935:1935 -p 3478:3478 -p 3478:3478/udp -v $(pwd)/letsencrypt:/etc/letsencrypt bigbluebutton -h <HOST_NAME> -i <HOST_IP>
~~~

Make sure you provide the host IP of the server on which you run the docker command. Once running, you can navigate to `http://<HOST_IP>` to access your BigBlueButton server.

