# Resumo dos Comandos Linux

Este documento fornece um resumo dos comandos Linux mais comuns, organizados de forma didática para facilitar a compreensão e o uso.

## 1. Iniciando um Contêiner Docker

- **`docker run -it ubuntu`**: Este comando inicia um contêiner interativo baseado na imagem do Ubuntu. O `-it` permite que você interaja com o terminal do contêiner.

## 2. Gerenciamento de Pacotes

- **`apt update`**: Atualiza a lista de pacotes disponíveis e suas versões, mas não instala ou atualiza nenhum pacote.
- **`apt list`**: Lista todos os pacotes disponíveis e instalados no sistema.
- **`apt install <pacote>`**: Instala um pacote específico. Substitua `<pacote>` pelo nome do pacote desejado.
- **`apt remove <pacote>`**: Remove um pacote específico do sistema.

## 3. Navegação e Manipulação de Arquivos

- **`pwd`**: Exibe o diretório de trabalho atual (Print Working Directory).
- **`ls -l`**: Lista os arquivos e diretórios no diretório atual com detalhes, como permissões, proprietário e tamanho.
- **`ls -1`**: Lista os arquivos e diretórios em uma única coluna.
- **`touch <arquivo>`**: Cria um novo arquivo vazio ou atualiza a data de modificação de um arquivo existente.
- **`mv <origem> <destino>`**: Move ou renomeia arquivos ou diretórios.
- **`rm <arquivo>`**: Remove um arquivo específico.
- **`rm -r <diretório>`**: Remove um diretório e todo o seu conteúdo recursivamente.

## 4. Visualização de Conteúdo

- **`cat <arquivo>`**: Exibe o conteúdo de um arquivo no terminal.
- **`echo <texto>`**: Exibe uma linha de texto no terminal.
- **`echo $0`**: Exibe o nome do script ou shell atual.

## 5. Redirecionamento e Concatenção

- **`>`**: Usado para redirecionar a saída de um comando para um arquivo, sobrescrevendo o conteúdo existente.
  - **Exemplo**: `echo hi docker > docker.txt` cria ou sobrescreve o arquivo `docker.txt` com o texto "hi docker".

## 6. Busca e Processos

- **`grep <padrão>`**: Busca por um padrão específico dentro de arquivos ou na saída de outros comandos.
- **`find <caminho> -name <nome>`**: Busca por arquivos e diretórios em um caminho específico com o nome fornecido.
- **`ps`**: Exibe uma lista dos processos em execução no sistema.
- **`kill <PID>`**: Envia um sinal para terminar um processo específico, onde `<PID>` é o ID do processo.

## 7. Identidade do Usuário

- **`whoami`**: Exibe o nome do usuário atual que está logado no sistema.

---

Esses comandos são fundamentais para a navegação e manipulação de arquivos em sistemas Linux, além de serem essenciais para o gerenciamento de pacotes e processos em contêineres Docker.

## Gerenciando Usuários

- **`useradd`**: Comando para adicionar um novo usuário.
- **`useradd -m andre`**: Adiciona um novo usuário chamado "andre" com um diretório home.
- **`usermod`**: Modifica as propriedades de um usuário existente.
- **`userdel`**: Remove um usuário do sistema.
- **`docker ps`**: Lista os contêineres em execução e fornece um ID.
- **`docker exec -it -u andre <ID> bash`**: Acessa um contêiner em execução como o usuário "andre".

## Gerenciando Grupos

- **`groups <nome>`**: Exibe os grupos aos quais um usuário pertence.
- **`groupadd <nome do grupo>`**: Cria um novo grupo.
- **`usermod -G docker <nome>`**: Adiciona um usuário a um grupo existente, como o grupo "docker".

## Permissões de Arquivos

- **`chmod u+x <nome do arquivo ou diretório>`**: Adiciona permissão de execução para o usuário no arquivo ou diretório especificado.

---

Esses comandos são essenciais para a administração de usuários e grupos, bem como para a configuração de permissões em sistemas Linux.