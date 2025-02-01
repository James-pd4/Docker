# Guia de Comandos Docker

Este documento apresenta os principais comandos do Docker relacionados a containers, volumes e manipulação de arquivos. Cada comando é explicado com exemplos práticos para facilitar o aprendizado.

---

## **1. Listar Containers em Execução**
### Comando:
```bash
docker ps
```

Explicação:
Exibe uma lista de todos os containers que estão atualmente em execução. Mostra informações como o ID do container, nome, imagem utilizada, status, portas expostas, entre outros.

## 2. Executar um Container em Segundo Plano

### Comando:
```bash
docker run -d app:v2
```
Explicação:
Executa um container com a imagem app:v2 em modo "detached" (segundo plano), permitindo que você continue utilizando o terminal enquanto o container roda.


## 3. Executar um Container com Nome Personalizado
### Comando:
```bash
docker run -d --name manga app:v2
```
Explicação:
Além de executar o container em segundo plano, este comando atribui o nome manga ao container, facilitando sua identificação.


## 4. Obter Ajuda sobre Logs
### Comando:
```bash
docker logs --help
```
Explicação:
Exibe informações sobre como usar o comando docker logs, que é utilizado para visualizar os logs de um container.



##  5. Mapear Portas entre o Host e o Container
### Comando:
```bash
docker run -d -p 80:3000 --name banana app:v2
ou
docker run -dp 80:3000 --name banana app:v2

```

Explicação:
O parâmetro -p 80:3000 mapeia a porta 3000 do container para a porta 80 do host, permitindo o acesso à aplicação do container através da porta 80.
O -d executa o container em segundo plano.
O --name banana atribui o nome banana ao container.




##  6. Executar Comandos Dentro de um Container
### Comando:
```bash
docker exec banana ls
```
Explicação:
Executa o comando ls dentro do container chamado banana. Isso permite acessar informações ou executar comandos diretamente no sistema de arquivos do container.


##  7. Parar e Iniciar Containers
### Comando:
```bash
docker stop banana
docker start banana
```

Explicação:
docker stop banana: Para o container chamado banana.
docker start banana: Reinicia o container chamado banana.


##  8. Remover Containers
### Comando:
```bash
docker rm -f manga
```
Explicação:
Remove o container chamado manga. O parâmetro -f força a remoção, mesmo que o container esteja em execução.


##  9. Listar Todos os Containers (Incluindo os Parados)
### Comando:
```bash
docker ps -a
```
Explicação:
Exibe uma lista de todos os containers, incluindo aqueles que estão parados.



##  10. Criar um Volume
### Comando:
```bash
docker volume create app-dados
```

Explicação:
Cria um volume chamado app-dados. Volumes são usados para armazenar dados persistentes que não são apagados quando o container é removido.



## 11. Inspecionar um Volume
### Comando:
```bash
docker volume inspect app-dados
```
Explicação:
Exibe informações detalhadas sobre o volume app-dados, como o local onde ele está armazenado no sistema de arquivos do host.



## 12. Montar um Volume em um Container
### Comando:
```bash
docker run -d -p 3000:3000 --name kiwi -v app-dados:/app/dados app:v2
```

Explicação:
O parâmetro -v app-dados:/app/dados monta o volume app-dados no diretório /app/dados dentro do container.
Isso permite que os dados armazenados no volume sejam acessados e persistam mesmo após a remoção do container.




## 13. Acessar o Terminal Interativo de um Container
### Comando:
```bash
docker exec -it kiwi sh
```
Explicação:
Abre um terminal interativo dentro do container chamado kiwi, permitindo que você execute comandos diretamente no ambiente do container.



## 14. Copiar Arquivos de um Container para o Host
### Comando:
```bash
docker cp kiwi2:/app/teste.txt .
```

Explicação:
Copia o arquivo teste.txt do diretório /app dentro do container kiwi2 para o diretório atual no host.

