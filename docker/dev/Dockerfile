# Utilizar una variable para la versión de Node.js
ARG NODE_VERSION=latest
FROM node:${NODE_VERSION}

# Establece el directorio de trabajo
WORKDIR /app

# Copia los archivos de configuración
COPY package*.json ./

# Instala solo las dependencias de desarrollo
RUN npm install --only=development

# Copia el resto del código de la aplicación
COPY . .

# Expone el puerto de desarrollo
EXPOSE 4200

# Comando para iniciar la aplicación en modo desarrollo
CMD ["npm", "start"]
