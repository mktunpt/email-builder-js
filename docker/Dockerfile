FROM node:20-alpine

RUN apk add --no-cache git

WORKDIR /app

RUN git clone https://github.com/mktunpt/email-builder-js.git .

WORKDIR /app/packages/editor-sample
RUN npm install && npm run build

EXPOSE 5173

CMD ["npm", "run", "preview", "--", "--host", "0.0.0.0"]
