# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
FROM node:6-alpine

EXPOSE 3000

RUN apk add --no-cache tini

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean --force

COPY . .

CMD [ "/sbin/tini", "--", "node", "./bin/www" ]
#Then it needs to run 'npm install' to install dependencies from that file.
#To keep it clean and small, run npm cache clean --force after the above, in the same RUN command.
#Then it needs to copy in all files from current directory into the image.
#Then it needs to start the container with the command /sbin/tini -- node ./bin/www.
# Be sure to use JSON array syntax for CMD. (CMD [ "something", "something" ])
