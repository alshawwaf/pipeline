FROM alpine

MAINTAINER "Khalid AL-Shwwwaf" <alshawwaf@gmail.com>

RUN wget https://releases.hashicorp.com/terraform/1.0.11/terraform_1.0.11_linux_amd64.zip
RUN unzip terraform_1.0.11_linux_amd64.zip && rm terraform_1.0.11_linux_amd64.zip
RUN mv terraform /usr/bin/terraform

ENTRYPOINT [ "terraform" ]

USER nobody:nobody