FROM nikolaik/python-nodejs:python3.9-nodejs19-slim

WORKDIR /amplify/src

RUN apt update

RUN apt install -y git curl unzip

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN ./aws/install
RUN rm awscliv2.zip

RUN npm install -g @aws-amplify/cli

RUN npm install aws-amplify @aws-amplify/ui-react@1.x.x
