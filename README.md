# docker-machine-gcp

docker run -d -p 8500:8500 ypmnprime/consul:latest -server -bootstrap -advertise=10.128.0.7 -ui-dir /ui


docker run -d swarm create.

docker-machine create --driver google --google-project halogen-obelisk-269703 \
--google-zone us-central1-a \
--google-machine-type n1-standard-2 \
--swarm \
--swarm-master \
--swarm-discovery token://87fd7b6bd42dc85b2cf22ead564c1853c69d0242a7125a234177f79c3664e68a \
--swarm-strategy spread \
--swarm-opt heartbeat=5s \
swarm-manager




docker-machine create --driver google --google-project halogen-obelisk-269703 \
--google-zone us-central1-a \
--google-machine-type n1-standard-1 \
node01


docker-machine create --driver google --google-project halogen-obelisk-269703 \
--google-zone us-central1-a \
--google-machine-type n1-standard-1 \
node02

-----------------------------------------on swarm-manager --------------
docker-machine ssh swarm-manager


sudo docker stop $(sudo docker ps -q) 
  
sudo docker run -d -p 3376:3376 -v /etc/docker/:/certs:ro swarm manage --tlsverify --tlscacert=/certs/ca.pem --tlscert=/certs/server.pem --tlskey=/certs/server-key.pem -H tcp://0.0.0.0:3376 --strategy spread --advertise 34.200.230.45:3376 consul://34.205.255.243:8500

sudo docker ps 

----------------------------------------- on node01 and node02 ----------------

------------------------------------------on node01
docker-machine ssh node01

sudo docker stop $(sudo docker ps -q)

sudo docker run -d swarm join --advertise 34.205.50.43:2376 consul://34.205.255.243:8500

sudo docker ps



----------------------------------------- on node02 


docker-machine ssh node01

sudo docker stop $(sudo docker ps -q)

sudo docker run -d swarm join --advertise 34.205.50.43:2376 consul://34.205.255.243:8500

sudo docker ps


The cluster creation has been done
Now test the cluster:
Login to base-machine and switch to root user

mkdir -p ~/.docker
cd ~/.docker
copy the swarm-manager certificates to .docker folder.

cp -r /home/ubuntu/.docker/machine/machines/swarm-manager/*.pem* ~/.docker/
export the env for connecting the swarm-manager

NOTE : change the tcp IP address with swarm-manager IP and this command will work for current terminal only

export DOCKER_HOST=tcp://34.200.230.45:3376 DOCKER_TLS_VERIFY=1
Check the swarm API version with below command

docker version --format '{{.Server.Version}}'
Now run the a test conatiner in cluster :

docker run -d ngnix 
