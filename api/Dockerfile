# Image de build
FROM node:alpine 

# Défine le répertoire par défault
WORKDIR /app

COPY dist dist
COPY node_modules node_modules

CMD node /app/dist/main.js