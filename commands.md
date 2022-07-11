# Commands

## dev-mode container

Linux

```bash
docker run -dp 3000:3000 \
     -w /app -v "$(pwd):/app" \
     node:12-alpine \
     sh -c "yarn install && yarn run dev"
```

Windows

```PS
docker run -dp 3000:3000 `
     -w /app -v "$(pwd):/app" `
     node:12-alpine `
     sh -c "yarn install && yarn run dev"
```

Apple silicon Mac or another ARM64 device

```zsh
docker run -dp 3000:3000 \
     -w /app -v "$(pwd):/app" \
     node:12-alpine \
     sh -c "apk add --no-cache python2 g++ make && yarn install && yarn run dev"
```

## MySQL container

Linux

```bash
docker run -d \
  --network todo-app --network-alias mysql \
  -v todo-mysql-data:/var/lib/mysql \
  -e MYSQL_ROOT_PASSWORD=secret \
  -e MYSQL_DATABASE=todos \
  mysql:5.7
```

Windows

```PS
docker run -d `
  --network todo-app --network-alias mysql `
  -v todo-mysql-data:/var/lib/mysql `
  -e MYSQL_ROOT_PASSWORD=secret `
  -e MYSQL_DATABASE=todos `
  mysql:5.7
```

## App container

```bash
docker build -t getting-started .
docker run -dp 3000:3000 getting-started
```

Push container

```bash
docker tag getting-started babis99/getting-started
docker push babis99/getting-started
```
