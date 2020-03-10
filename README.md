# docker-machine-gcp


sudo docker run -d -p 3376:3376 -v /etc/docker/:/certs:ro swarm manage --tlsverify --tlscacert=/certs/ca.pem --tlscert=/certs/server.pem --tlskey=/certs/server-key.pem -H tcp://0.0.0.0:3376 --strategy spread --advertise 34.70.150.251:3376 consul://35.226.201.10:8500



sudo docker run -d swarm join --advertise 35.238.77.207:2376 consul://35.226.201.10:8500


export DOCKER_HOST=tcp://34.70.150.251:3376 DOCKER_TLS_VERIFY=1
