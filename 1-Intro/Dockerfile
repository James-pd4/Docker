# Usar a imagem oficial do Node.js como base
FROM node:alpine

# Definir o diretório de trabalho
WORKDIR /app

# Copiar o package.json e o package-lock.json (se existirem)
COPY package*.json ./

# Copiar o restante dos arquivos da pasta atual para o diretório de trabalho
COPY . .

# Comando para rodar a aplicação
CMD ["node", "app.js"]


# Esse comando é executado no terminal para constrir a imagem
# docker build -t hi-docker