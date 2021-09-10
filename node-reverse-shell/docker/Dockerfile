# Run node reverse shell in a container
#
# docker run -p 3000:3000 -d appsecco/node-reverse-shell
#

FROM node:14.17.6-buster
MAINTAINER Madhu Akula <madhu@appsecco.com>

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

RUN npm install -g pm2 http url path

COPY server.js /usr/src/app/
COPY animals.json /usr/src/app/

EXPOSE 3000
CMD [ "pm2", "startup" ]
CMD [ "pm2", "stop", "app" ]
CMD [ "pm2", "start", "server.js", "--name", "app", "--no-daemon" ]
