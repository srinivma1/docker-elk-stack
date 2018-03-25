# docker-elk-stack

1. First create a docker swarm by following URLs:
https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/
https://botleg.com/stories/monitoring-docker-swarm-with-cadvisor-influxdb-and-grafana/

2. Follow the URL below for creating ELK stack:
https://botleg.com/stories/log-management-of-docker-swarm-with-elk-stack/


Run following commands for deploying elk stack:
docker stack deploy -c docker-stack.yml elk

To see the services in the stack,  use the following  command :

docker stack services elk

To see the running containers in the stack, use the following command:

 docker stack ps elk
 
 Run following command for deploying example:
 docker stack deploy -c nginx.yml nginx
 
 Open Kibana:
  http://docker-machine ip manager
  
  Open example:
  http://docker-machine ip manager:8000
  
  
  Use the query docker.image: nginx AND (200 OR 304) in Kibana
  
  
  once done, issue following commands:
  
  docker stack rm elk
docker stack rm nginx

Once done with the VMs created for the demo, you can stop and remove then with the following commands,

docker-machine stop manager agent1 agent2
docker-machine rm -f manager agent1 agent2
