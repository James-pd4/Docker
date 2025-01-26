# Resumo de Estudo sobre Docker

Este documento fornece um resumo sobre o uso de imagens no Docker, incluindo comandos essenciais para gerenciar imagens e contêineres, além de passos iniciais para a criação de imagens e uma explicação sobre o Dockerfile.

## 1. Passos Iniciais para Criação de Imagens

1. **Instalação do Docker**: Certifique-se de que o Docker está instalado e funcionando corretamente em seu sistema.
2. **Criar um Dockerfile**: Crie um arquivo chamado `Dockerfile` (sem extensão) em um diretório de sua escolha. Este arquivo conterá as instruções para construir sua imagem.
3. **Definir as Instruções no Dockerfile**: Abra o Dockerfile em um editor de texto e comece a definir as instruções necessárias, como a imagem base, instalação de pacotes e configuração do ambiente.

## 2. O que é um Dockerfile?

- **Definição**: O Dockerfile é um arquivo de texto que contém uma série de instruções que o Docker utiliza para construir uma imagem. Ele pode ser visto como uma "receita" que descreve como a imagem deve ser criada, incluindo a instalação de pacotes, a configuração de variáveis de ambiente e a definição de comandos a serem executados quando um contêiner é iniciado a partir da imagem.

- **Estrutura Básica**:
  - **FROM**: Define a imagem base a ser utilizada.
  - **RUN**: Executa comandos durante a construção da imagem, como a instalação de pacotes.
  - **COPY**: Copia arquivos do sistema de arquivos do host para o sistema de arquivos da imagem.
  - **CMD**: Especifica o comando padrão a ser executado quando um contêiner é iniciado a partir da imagem.

## 3. Como Criar uma Imagem

Para criar uma imagem a partir de um Dockerfile, siga os passos abaixo:

1. **Escreva o Dockerfile**: Defina as instruções necessárias no Dockerfile. Por exemplo:
   ```dockerfile
   FROM node:14
   WORKDIR /app
   COPY package*.json ./
   RUN npm install
   COPY . .
   CMD ["node", "app.js"]


- **Comando**: `docker build -t nome_da_imagem:tag .`

## 4. Executando um Contêiner

- **Comando**: `docker run -dp 3000:3000 app`
  - **Descrição**: Este comando inicia um contêiner a partir da imagem "app" em modo destacado (`-d`), mapeando a porta 3000 do contêiner para a porta 3000 da máquina host (`-p`). Isso permite que a aplicação dentro do contêiner seja acessada através de `http://localhost:3000`.

## 5. Criando Versões para Imagens

- **Comando**: `docker image tag app:latest app:v1.0.0`
  - **Descrição**: Este comando cria uma nova tag para a imagem "app", permitindo versionar a imagem. A versão "v1.0.0" pode ser utilizada para identificar essa versão específica da imagem.

## 6. Renomeando uma Imagem

- **Comando**: `docker image tag 047dd74b803a jamespd4/app:v1`
  - **Descrição**: Este comando renomeia uma imagem existente (identificada pelo ID `047dd74b803a`) para "jamespd4/app" com a tag "v1". Isso é útil para organizar e identificar imagens em repositórios.

## 7. Subindo Imagem para o Repositório Docker

- **Comando**: `docker push jamespd4/app:v1`
  - **Descrição**: Este comando envia a imagem "jamespd4/app" com a tag "v1" para o Docker Hub ou outro repositório configurado. É necessário estar autenticado no repositório para realizar o push.

## 8. Compactando uma Imagem

- **Comando**: `docker image save -o appv1.tar app:v2`
  - **Descrição**: Este comando salva a imagem "app" com a tag "v2" em um arquivo tar chamado "appv1.tar". Isso é útil para transferir a imagem entre sistemas ou para backup.

---

Esses comandos e conceitos são fundamentais para o gerenciamento de imagens e contêineres no Docker, permitindo que desenvolvedores criem, versionem e distribuam suas aplicações de forma eficiente.