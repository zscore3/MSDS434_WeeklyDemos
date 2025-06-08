Week 9  
Prometheus  
1. Launch New Instance t2 micro & connect in
2. Run Code
   sudo apt update
   sudo snap install docker
   sudo docker  pull prom/prometheus
   sudo docker network create network
   sudo docker volume create prometheus-data
   vi prometheus.yml
   #paste from git
   sudo docker container run --name prometheus -v prometheus.yml -v prometheus-data:/prommetheus -p 9090:9090 prom/prometheus
3. Modify security groups & grab DNS to throw into browser
4. hit graph & display a measurement

Grafana
1. Establish a second connection to the same instance
2. run code
   sudo docker pull grafana/grafana
   sudo docker volume create grafana-data
   sudo docker container run -v grafana-data -p 3000:3000 --name grafana --network network grafana/grafana
3. paste address in browser
4. username: admin password:admin
5. add data source > prometheus
6. url = DNS:9090
7. save & test
8. administration
9. build a dash
10. build a visualization
11. select a metric
12. run query
