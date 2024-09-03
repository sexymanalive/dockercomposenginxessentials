## Note 
for working with docker compose and nginx web server 

### Create repo with gh command 

```bash

gh auth login # -> web, token 
# token -> permission 3 ( repo , org , admin:org)
gh auth status # show the status of auth 

gh repo create dockercomposenginxessentials --public
gh repo view dockercomposenginxessentials --json sshUrl | jq -r '.sshUrl'
gh repo view dockercomposenginxessentials --json url | jq -r '.url'

git init 
git remote add origin $(gh repo view dockercomposenginxessentials --json url | jq -r '.url'
)

git remote -v # show origin of the project 
```

## Docker compose related command 

```bash

docker compose config 
docker compose config --services 

docker compose down 
docker compse down --volumes or -v # erase the volumes
docker logs -f container-name 
docker compose logs first-nginx second-nginx third-nginx
```


## Apache Benchmark 

```bash
sudo apt update 
sudo apt install apache2-utils -y 
ab 

ab -n [number of requests] -c [concurrent requests] http://[hostname]/
ab -n 1000 -c 10 http://localhost:8888/

```