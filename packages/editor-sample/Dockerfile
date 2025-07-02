# Stage 1: build static assets do editor
FROM node:18-alpine AS builder

WORKDIR /app

COPY packages/editor-sample/package.json packages/editor-sample/package-lock.json? ./
COPY packages/editor-sample/ ./
RUN npm install && npm run build

# Stage 2: serve via nginx
FROM nginx:stable-alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
