FROM node:12.4-alpine

WORKDIR /usr/app/test

# Copy package file seperately to prevent rebuilding and Minimizing cache busting
COPY ./package.json ./
RUN npm install

COPY ./ ./

CMD ["npm", "start"]
