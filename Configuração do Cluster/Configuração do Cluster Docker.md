# Configurando um Cluster Local  usando o RavenDB e Docker
Para essa demonstração usaremos a versão gratuita do RavenDB que permite criar um cluster com até 3 nós. Para fazer essa etapa, será necessário ter obtido uma licença grátis, disponível neste link: 

## Subindo uma instância Líder (Leader)
Usando o Docker, criaremos um container com o servidor do RavenDB, com o seguinte comando no terminal:
 
 ```
docker run --name "nodeA" -d -p 8080:8080 -p 38888:38888 ravendb/ravendb
 ```

Onde cada parâmetro significa:
- `docker`: software container onde criaremos nossos servidores.
- `run`: comando run do Docker que cria um container isolado com processo.
-  `--name "nodeA"`: nome (ou apelido) dado ao container para conseguirmos acessar em outros comandos.
- `-d`: container em modo *detatched*, para que possamos usar o mesmo terminal para os próximos comandos.
- `-p 8080:8080`: mapeamento das portas IP da máquina hospedeira e do container, no formato \<portaHospedeira>:\<portaContainer>.
- `-p 38888:38888`: mapeamento das portas TCP da máquina hospedeira e do container.
- `ravendb/ravendb`: imagem do RavenDB a ser usada no container.

Mais informações na documentação do comando [run](https://docs.docker.com/engine/reference/run). 

## Subindo instâncias Membro (Member)
Criaremos agora mais dois containers com os seguintes comandos no terminal:
 
 ```
docker run --name "nodeB" -d -p 8081:8080 ravendb/ravendb
 ```
 
 ```
docker run --name "nodeC" -d -p 8082:8080 ravendb/ravendb
 ```

## Encontrando o IP e porta de cada instância
Podemos encontrar o IP e a porta de cada container usando o comando:
 ```
 sudo docker network inspect bridge
```
Buscando o endereço de cada nó, similar a seguinte saída:
```
"Containers": {
            {
                "Name": "nodeA",
                "IPv4Address": "172.17.0.2/16",
                "IPv6Address": ""
            }
        }
```

## Definindo os nós do Cluster

Definiremos o nó A como líder e os nós B e C como membros, para construir o cluster.

### Membros
Nos nós B e C a configuração é bem simples. Acessando pelo navegador endereço correspondente ao IP encontrado anteriormente na porta 8080, podemos fazer a configuração inicial do nó:

Aceite os termos de uso:
![termos de uso](https://github.com/AndersonGarrote/PMD/blob/master/Configuração%20do%20Cluster/Opera%20Instantâneo_2019-11-06_224010_localhost.png)

Selecione o modo não seguro (para fins de demonstração):
![escolher modo de configuração](https://github.com/AndersonGarrote/PMD/blob/master/Configuração%20do%20Cluster/Captura%20de%20tela%20de%202019-11-06%2022-40-44.png)
 
Digite o IP correspondente no campo indicado:
![definir ip e porta](https://github.com/AndersonGarrote/PMD/blob/master/Configuração%20do%20Cluster/Opera%20Instantâneo_2019-11-06_224324_172.17.0.3.png)

Clique em Next para continuar. 

Reinicie o servidor:
![reiniciar servidor](https://github.com/AndersonGarrote/PMD/blob/master/Configuração%20do%20Cluster/Captura%20de%20tela%20de%202019-11-06%2022-41-10.png)

Faça o mesmo processo para o outro nó membro.

### Líder
O processo é bem parecido, seguindo os mesmo passos, com o detalhe de selecionar apenas a opção *Create new Cluster* e definir o nome do nó, na tela de configuração de endereços:

![opçao cluster](https://github.com/AndersonGarrote/PMD/blob/master/Configuração%20do%20Cluster/Opera%20Instantâneo_2019-11-06_224426_172.17.0.3.png)

Clique em Next e ao final, reinicie o nó:

![reiniciar servidor](https://github.com/AndersonGarrote/PMD/blob/master/Configuração%20do%20Cluster/Captura%20de%20tela%20de%202019-11-06%2022-41-10.png)

### Definindo a topologia
Com o navegador aberto no endereço do nó A, usaremos o RavenStudio para definir a topologia do *cluster*.SH

>Essa configuração pode mudar com o passar do tempo, pois devido a questões como problemas com a rede ou sobrecarga de recursos, pode haver uma votação e um novo líder ser escolhido.


## Criando um banco com replicação
Vamos agora criar um banco com replicação, mantendo os nós replicados em todos os nós.


Fonte: https://ravendb.net
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgxMjA2NjExOSwtMTU4ODk3MTM0NiwxNT
g1MDE4MTQzLC0xNzcwNjk1MjAyLC0yMDA1MTcxOTM2LC0xMDE1
OTQ4Mzk3LC00NzU4NDUzMzUsNjQzODM1NDk2LC0xMjYxMzYzNj
MwLDMxNDEwNjAyXX0=
-->
