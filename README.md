# docker-machine-gcp


docker run -d -p 8500:8500 ypmnprime/consul:latest -server -bootstrap -advertise=10.128.0.7 -ui-dir /ui


docker run -d swarm create.

docker-machine create --driver google --google-project halogen-obelisk-269703 \
--google-zone us-central1-a \
--google-machine-type n1-standard-1 \
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


sudo docker run -d -p 3376:3376 -v /etc/docker/:/certs:ro swarm manage --tlsverify --tlscacert=/certs/ca.pem --tlscert=/certs/server.pem --tlskey=/certs/server-key.pem -H tcp://0.0.0.0:3376 --strategy spread --advertise 34.70.150.251:3376 consul://35.226.201.10:8500



sudo docker run -d swarm join --advertise 35.238.77.207:2376 consul://35.226.201.10:8500


export DOCKER_HOST=tcp://34.70.150.251:3376 DOCKER_TLS_VERIFY=1
