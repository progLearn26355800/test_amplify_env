FROM nikolaik/python-nodejs:python3.9-nodejs19-slim

WORKDIR /amplify

RUN apt update && apt install -y git curl unzip

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN ./aws/install
RUN mkdir ~/.aws
RUN rm awscliv2.zip
RUN rm -rf aws
RUN curl -kL "https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip" -o "aws-sam-cli.zip"
RUN unzip aws-sam-cli.zip -d sam-installation
RUN ./sam-installation/install
RUN rm -rf sam-installation
RUN rm aws-sam-cli.zip

RUN npm install -g @aws-amplify/cli

RUN npm install aws-amplify @aws-amplify/ui-react@1.x.x
