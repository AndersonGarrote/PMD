# Disponibilidade

Algumas ações, como criar banco de dados ou índices requerem um consenso do cluster, para isto o RavenDB utiliza o  _Rachis_, uma implementação proprietária de algoritmo de consenso para sistemas distribuídos. Requerendo um quórum de N/2 + 1 processos para que seja possível a eleição de líder.

No RavenDB temos o banco de dados replicado entre vários nós, um grupo de nós que mantém o mesmo banco de dados replicado é chamado de *Group Database* e, o fator de replicação pode ser definido, lembrando que a versão gratúita do RavenDB suporta fator de replicação de até 3 nós. Documentos são mantidos em sincronia em nós pertencentes à um _Database Group_ com uma replicação _master to master_

Tendo um cluster com vários nós é possível realizar requisições espalhadas em vários nós, com a finalidade de maior desempenho, porém a replicação nos permite mesmo com a maioria do _cluster_ inoperante, desde que tenhamos um único nó vivo, temos acesso à leituras e escritas no banco.

Para exemplificar iremos criar uma topologia de 3 nós sendo o nó **A** definido como *Master* e os nós **B** e **C** como *Members*.

![enter image description here](https://lh3.googleusercontent.com/MgNJC99AoQCBJOjNjTcNeUJhisnHGXXEI4_zZZhRPM97eh55lO5dCfuvAhYbtD-FTMNzzPb51as)

Existem quatro tipos de nó:

 ![Tipos de nó](https://lh3.googleusercontent.com/uRTulWUIS99gzAZh4LWxYenhbIln2SIYEmf3LzglHeBlPU_Ab_MTfRAIN-AR5fJrjp2OjfBE5jQ)
- *Leader*: Nó líder do *Group Database*.
- *Member*: Nó membro do *Group Database*, pode se tornar um Líder em caso de eleição.
- *Watcher*: Nó membro com menos previlégios; não pode ser eleito como Líder em caso de votação, não participando do Quórum.
- *Promotable*: Estado de nó aplicável apenas em caso de eleição; um nó elegível deve ser membro e estar em pleno funcionamento.

Ao derrubarmos o nó **A** teremos uma nova eleição que será realizada pelo quórum restante de Membros:

![enter image description here](https://lh3.googleusercontent.com/_Y01ZYw1RYHJqHdWXL8QSF6RBqicHRjaEIVhwjMkcWDwM-03O3RZouAY0HJ2PQy69bfoSLcBtZU)

Em um outro cenário onde **C** foi rebaixado, ficando como um _Watcher_. Ao derrubarmos o atual _Leader_ **B** o quórum de _Members_ não é suficiente para eleger outro nó, desta forma a eleição fica esperando um quórum suficiente (N/2 + 1):

![enter image description here](https://lh3.googleusercontent.com/3nzanwWTxJskAwdI-GX9YnNXpGNwEmVgcajBcyU7a8xvMuFGtQf9vlCl3ioocI9tFTKkhVjdaN4)


Para exemplificar a replicação entre os nós criaremos um Banco de Dados chamado **** com uma coleção chamada ****
--- 
---
---
Uma _Task_ é definida por um _Group Database_ e é atribuída à um nó somente.
Um nó também pode ser um nó Mentor, isto ocorre quando este fica responsável por atualizar um nó recuperado, que identifica um tipo de task (_Rehab_), ou um nó que acabou de entrar no Grupo (_Promotable_).


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTcxMjI5MDUxOF19
-->