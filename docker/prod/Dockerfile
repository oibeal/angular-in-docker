# Utilizar una variable para la versión de Node.js
ARG NODE_VERSION=latest
FROM node:${NODE_VERSION} AS build

# Establece el directorio de trabajo
WORKDIR /app

# Copia los archivos de configuración
COPY package*.json ./

# Instala solo las dependencias de producción
RUN npm install

# Copia el resto del código de la aplicación
COPY . .

# Construye la aplicación para producción
RUN npm run build --prod -- --output-path=dist/angular-app

# Usa una imagen base de Nginx para servir la aplicación
FROM nginx:alpine

# Preparar servidor para recibir datos
COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf

# Copia los archivos de construcción a Nginx
COPY --from=build /app/dist/angular-app/browser/* /usr/share/nginx/html

# Expone el puerto de producción
EXPOSE 80

# Comando para iniciar Nginx
CMD ["nginx", "-g", "daemon off;"]