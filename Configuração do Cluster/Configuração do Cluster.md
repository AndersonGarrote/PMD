# Configurando um Cluster usando o RavenDB
Para essa demonstração usaremos a versão gratuita do RavenDB que permite criar um cluster com até 3 nós. Para fazer essa etapa, será necessário ter realizado a 

## Subindo uma instância Líder (Leader)
Usando o Docker, criaremos um container com o servidor do RavenDB, com o seguinte comando:
 
 ``
docker run --name "nodeA" -d -p 8080:8080  ravendb/ravendb
 ``

Onde cada parâmetro significa:
- `docker`: software container onde criaremos nossos servidores
- `run`: comando run do Docker que cria um processo 
 
## Subindo instâncias Membro (Member)

## Definindo os nós do Cluster

## Criando um banco com replicação
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMyNDY1NDQ2LC0xMTI1MDM2MjY2LC0yND
g4Nzg0NzUsMzQ2MTE1ODE5XX0=
-->