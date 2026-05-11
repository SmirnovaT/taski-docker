FROM node:22

RUN apt-get update && apt-get install -y ca-certificates && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm config set strict-ssl false && npm ci

COPY . .
RUN npm run build

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]