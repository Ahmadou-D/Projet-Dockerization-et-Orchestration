FROM node:18-alpine

ENV NODE_ENV=production

WORKDIR /app

COPY package*.json ./

RUN --mount=type=cache,target=/app/.npm \
    npm set cache /app/.npm && \
    npm ci --only=production

COPY --chown=node:node . .

USER node

EXPOSE 8888

CMD ["node", "server.js"]