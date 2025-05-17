FROM node:18-alpine

# Instala herramientas necesarias
RUN apk add --no-cache bash curl

# Crea directorio de trabajo
WORKDIR /usr/src/app

# Copia package.json y pnpm-lock
COPY package*.json ./
COPY pnpm-lock.yaml ./

# Instala pnpm y dependencias
RUN npm install -g pnpm && pnpm install --frozen-lockfile

# Copia todo el código
COPY . .

# Compila
RUN pnpm run build

# Expone el puerto
EXPOSE 5678

# Comando de arranque
CMD ["pnpm", "start"]
