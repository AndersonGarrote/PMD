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

Prosseguiremos com a configuração, acessando o endereço: 

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
docker network inspect bridge
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
Nos nós B e C a configuração é bem simples. Acessando pelo navegador o endereço correspondente ao IP encontrado anteriormente na porta 8080, podemos fazer a configuração inicial do nó:

Aceite os termos de uso.

Selecione o modo não seguro (para fins de demonstração):
 
Digite o IP correspondente no campo indicado:

Clique em continua


>Essa configuração pode mudar com o passar do tempo, pois devido a questões como problemas com a rede ou sobrecarga de recursos, pode haver uma votação e um novo líder ser escolhido.


## Criando um banco com replicação
Vamos agora criar um banco com replicação, mantendo os nós replicados em todos os nós.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3Nzc5NzgxMzYsLTEyNjEzNjM2MzAsMz
E0MTA2MDJdfQ==
-->