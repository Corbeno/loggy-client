# loggy-client

## Install

Install docker/docker-compose
```bash
sudo apt update && sudo apt upgrade -y
```

```bash
sudo apt install docker.io -y
```

```bash
sudo usermod -aG docker cdc
```

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/v2.11.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
>Note: You can use a newer version of docker-compose if you want

```bash
sudo chmod +x /usr/local/bin/docker-compose
```

If using a proxy (which you most likely are in the CDC), configure docker to use it by the following

```bash
sudo systemctl edit docker.service
```

```
[Service]
Environment="HTTP_PROXY=http://199.100.16.100:3128"
Environment="HTTPS_PROXY=http://199.100.16.100:3128"
Environment="NO_PROXY=localhost,127.0.0.1"
```

```bash
sudo systemctl restart docker
```


Clone the repo
```bash
git clone https://github.com/Corbeno/loggy-client
```

```bash
cd loggy-client
```

edit ```promtail/promtail-config.yml``` and change any #TODOS


```bash
docker-compose up -d
```
>Note: You can omit the -d to see console output and veryify everything is working before running it in the again in the background




