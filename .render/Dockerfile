FROM node:18-alpine

# Instala herramientas necesarias
RUN apk add --no-cache bash curl git


# Crea el directorio de trabajo
WORKDIR /usr/src/app

# Copia archivos de configuración
COPY package*.json ./
COPY pnpm-lock.yaml ./
COPY . .

# Instala pnpm y dependencias
RUN npm install -g pnpm && pnpm install --no-frozen-lockfile

# Compila el proyecto
RUN pnpm run build

# Expone el puerto usado por n8n
EXPOSE 5678

# Comando correcto para ejecutar n8n desde pnpm
CMD ["pnpm", "n8n", "start"]
