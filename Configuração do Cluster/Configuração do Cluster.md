# Configurando um Cluster usando o RavenDB
Para essa demonstração usaremos a versão gratuita do RavenDB que permite criar um cluster com até 3 nós. Para fazer essa etapa, será necessário ter realizado a 

## Subindo uma instância Líder (Leader)
Usando o Docker, criaremos um container com o servidor do RavenDB, com o seguinte comando:
 
 ``
docker run --name "nodeA" -d -p 8080:8080  ravendb/ravendb
 ``

Onde cada parâmetro significa:
- `docker`: software container onde criaremos nossos servidores
- `run`: comando run do Docker que cria um container isolado com processo
-  `name
 
## Subindo instâncias Membro (Member)

## Definindo os nós do Cluster

## Criando um banco com replicação
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MjE1NDc2MDksLTExMjUwMzYyNjYsLT
I0ODg3ODQ3NSwzNDYxMTU4MTldfQ==
-->