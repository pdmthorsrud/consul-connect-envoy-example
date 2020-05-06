# consul-connect-envoy-example
Example of Consul Connect using Envoy as proxy


## Usage
* Run `docker build -t consul-envoy .`
* Run the docker-container with `docker run --rm -d -v$(pwd)/envoy_demo.hcl:/etc/consul/envoy_demo.hcl \
  --network host --name consul-agent consul:latest \
  agent -dev -config-file /etc/consul/envoy_demo.hcl
1c90f7fcc83f5390332d7a4fdda2f1bf74cf62762de9ea2f67cd5a09c0573641`
* run procxies with `docker run --rm -d --network host --name echo-proxy \
  consul-envoy -sidecar-for echo`
