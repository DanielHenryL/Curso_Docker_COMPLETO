FROM node:19.2-alpine3.16
# /app

# cd app
WORKDIR /app

# Destino /app
COPY package.json ./

# Instalar dependencias
RUN npm install

# Destino /app
COPY . .

# Realizar testing y luego se eliminara este archivo con su carpeta.
RUN npm run test

# Eliminar archivos y directorios no necesarios en PROD
RUN rm -rf test && rm -rf node_modules 

# Unicamente las dependencia de prod
RUN npm install --prod

# Comando run de la imagen
CMD [ "node", "app.js" ]
