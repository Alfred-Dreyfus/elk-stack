# Elastisearch-Logstash-Kibana Installation with Dockerfile

- As a prerequisite, Docker Engine with Docker-Compose will need to be installed and configured.

 

## Set up Docker's apt repository. (Source:  https://docs.docker.com/engine/install/ubuntu/ )

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

## Install the Docker packages.

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

- (Optional) Verify that the Docker Engine installation is successful by running the hello-world image. 

sudo docker run hello-world
```

## Install the Compose plugin ( Source: https://docs.docker.com/compose/install/linux/ )

- Update the package index, and install the latest version of Docker Compose:

```bash
sudo apt-get update
sudo apt-get install docker-compose-plugin

- (Optional) Verify that Docker Compose is installed correctly by checking the version.

docker compose version
```

### Project Skeleton

```text
elk (folder)
|
|----readme.md
|----.env
|----docker-compose.yaml
|----logstash.conf
```

- Create .env file
- Create logstash.conf
- Create docker-compose.yaml



## Deploy with docker compose

```bash
sudo docker compose up -d
```

- After the application starts, navigate to below links in your web browser:

Elasticsearch: http://localhost:9200

Logstash: http://localhost:9600

Kibana: http://localhost:5601/api/status

