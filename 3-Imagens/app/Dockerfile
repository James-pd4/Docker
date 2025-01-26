FROM node:12-alpine

WORKDIR /app

#RUN addgroup dev && adduser -S -G andre dev
#cria um grupo chamado "dev" e um usuário do sistema chamado "dev", 
#que é adicionado ao grupo "andre"

#USER andre

COPY package.json .

RUN apk add --no-cache python2 g++ make

RUN yarn install --production

COPY . .

CMD ["node", "src/index.js"]

EXPOSE 3000

# docker run -dp 3000:3000 app

# Criar versões p/ images:  docker image tag app:latest app:v1.0.0

# renomeando uma imagem: docker image tag 047dd74b803a jamespd4/app:v1

# subir para o repositório docker: docker push jamespd4/app:v1

# compactar uma imagem:  docker image save -o appv1.tar app:v2

