# Code for Linux Days 2018 talk: Gitlab CI + Docker

    Ondrej Sika <ondrej@ondrejsika.com>
    https://github.com/ondrejsika/linuxdays2018

## Usage

### Clone

```
git clone git@github.com:ondrejsika/linuxdays2018.git
cd linuxdays2018
```

### Run locally on port 8000

```
PORT=8000 docker-compose -f docker-compose.yml -f docker-compose-ports.yml up
```

Open <http://localhost:8000>

### Run tests

```
docker-compose -f docker-compose.yml -f docker-compose-test.yml up --abort-on-container-exit test
docker-compose -f docker-compose.yml -f docker-compose-test.yml down
```

### Run on Traefik

Traefik must listen on network `traefik`, run traefik with ssl - <https://github.com/ondrejsika/traefik-ssl>

```
HOST=counter.127.0.0.1.xip.io docker-compose -f docker-compose.yml -f docker-compose-traefik.yml up
```

Open <http://counter.127.0.0.1.xip.io>