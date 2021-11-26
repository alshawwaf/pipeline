How to build a docker image for terraform 
***
Maintainer: Khalid Al-Shawwaf <alshawwaf@gmail.com>

1. write a docker file to download and unzip terraform in a container

```Dockerfile
FROM alpine

MAINTAINER "Khalid AL-Shwwwaf" <alshawwaf@gmail.com>

RUN wget https://releases.hashicorp.com/terraform/1.0.11/terraform_1.0.11_linux_amd64.zip
RUN unzip terraform_1.0.11_linux_amd64.zip && rm terraform_1.0.11_linux_amd64.zip
RUN mv terraform /usr/bin/terraform

USER nobody:nobody
```

2. build the container 

```bash 
docker build -t alshawwaf/terraform:1-0-11 .
```

3. push the container to your docker hub

```bash
docker push alshawwaf/terraform:1-0-11
```

4. To use, run the following command:

```bash
docker run -it alshawwaf/terraform:1-0-11 terraform --version
```

5. If you are using docker-compose, create a service as follows:

```Docker Compose
services:
  terraform:
    build: 
      context: ./terraform
      dockerfile: ./Dockerfile
```

6. Run the conainer using docker-compose with the terrafrom command

```
docker-compose run --rm terraform --version

Terraform v1.0.11
on linux_amd64
```