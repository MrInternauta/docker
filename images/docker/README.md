# RUN THE PROJECT
## Build the image
```bash
docker build -t mrinternauta/node_app:001 -f Dockerfile .
```

## Run container
```bash
docker run -p 3000:3000 mrinternauta/node_app:001
```

Build the image
docker build -t mrinternauta/node_app:001 -f Dockerfile .
Run project
docker run -p 3000:3000 mrinternauta/node_app:001
Run test
docker run -p 3000:3000 mrinternauta/node_app:001 npm test

<https://github.com/MrInternauta/Jenkins>
