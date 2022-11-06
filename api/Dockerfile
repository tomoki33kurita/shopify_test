FROM node:19-alpine3.15
WORKDIR /ec-api
ENV NODE_ENV production

RUN apk add --no-cache tini && npm i -g @nestjs/cli

COPY --chown=node:node ./ec-api/package.json ./ec-api/package-lock.json ./
RUN npm install --prod --frozen-lockfile

COPY --chown=node:node ./ec-api ./

ENTRYPOINT ["/sbin/tini", "--"]

# EXPOSE 7777

CMD ["npm", "run", "start"]

