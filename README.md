# python-flask-docker
Basic Python Flask app in Docker which prints the hostname and IP of the container

### Build application
Build the Docker image manually by cloning the Git repo.
```
$ git clone https://github.com/lvthillo/python-flask-docker.git
$ docker build -t lvthillo/python-flask-docker .
```

### Download precreated image
You can also just download the existing image from [DockerHub](https://hub.docker.com/r/lvthillo/python-flask-docker/).
```
docker pull lvthillo/python-flask-docker
```

### Run the container
Create a container from the image.
```
$ docker run --name my-container -d -p 8080:8080 lvthillo/python-flask-docker
```

Now visit http://localhost:8080
```
 The hostname of the container is 6095273a4e9b and its IP is 172.17.0.2. 
```

### Verify the running container
Verify by checking the container ip and hostname (ID):
```
$ docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-container
172.17.0.2
$ docker inspect -f '{{ .Config.Hostname }}' my-container
6095273a4e9b
```
To push our image to docker hub:
login to docker hub
bhavyashettyrai   passwd Ra..........3

docker tag flask/app bhavyashettyrai/flask-app:v1.0  (here flask app is the image name i have given during image build)

docker push bhavyashettyrai/flask-app:v1.0

access denied....
sudo docker login
username and password enter
docker push bhavyashettyrai/flask-app:v1.0 
now go and check your docker hub...image is pushed.
This image can pull anuone using below comand...
docker pull bhavyashettyrai/flask-app:v1.0 
