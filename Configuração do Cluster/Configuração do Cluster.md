# Configurando um Cluster usando o RavenDB
Para essa demonstração usaremos a versão gratuita do RavenDB que permite criar um cluster com até 3 nós. Para fazer essa etapa, será necessário ter realizado a 

## Subindo uma instância Líder (Leader)
Usando o Docker, criaremos um container com o servidor do RavenDB, com o seguinte comando:
 
 ``
docker run --name "nodeA" -d -p 8080:8080  ravendb/ravendb
 ``

Onde cada parâmetro significa:
- `docker`: software de container 
 
## Subindo instâncias Membro (Member)

## Definindo os nós do Cluster

## Criando um banco com replicação
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgxMjEwNjAyNiwtMTEyNTAzNjI2NiwtMj
Q4ODc4NDc1LDM0NjExNTgxOV19
-->