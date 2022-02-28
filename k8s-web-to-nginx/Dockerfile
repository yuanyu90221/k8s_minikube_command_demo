# stage 1 build the code
FROM node:16.12.0-alpine AS builder
RUN mkdir -p app
EXPOSE 3000
COPY package.json package-lock.json index.mjs app/
WORKDIR app/
RUN npm i
# stage 2
FROM node:16.12.0-alpine
COPY --from=builder app ./app
RUN chown -R node:node app
USER node
EXPOSE 3000
WORKDIR app
CMD ["node", "index.mjs"]