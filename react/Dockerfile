FROM node:15.13-alpine

RUN apk update && apk add git

RUN git clone https://github.com/danielglez4234/app-cameras-react-b

WORKDIR /app-cameras-react-b

ENV PATH="/app-cameras-react-b/node_modules/.bin:$PATH"

RUN chmod 777 package*.json

RUN npm install

RUN npm install -g react-scripts

RUN npm install react

RUN npm run build

CMD ["npm", "start"]
