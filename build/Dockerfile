FROM nikolaik/python-nodejs:python3.9-nodejs19-slim

WORKDIR /amplify/src

RUN apt update

RUN apt install -y git

RUN npm install -g @aws-amplify/cli

RUN npm install aws-amplify @aws-ampliffy/ui-react@1.x.x
