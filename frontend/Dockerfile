FROM node:18-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npminstall

COPY . .
RUN npm run build

FROM nginx:1.25-alpine
COPY --from=builder /app/dist /usr/share/nginx/html

CMD ["true"]
