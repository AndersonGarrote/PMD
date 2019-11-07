
## Escalabilidade

Se tratando de escalabilidade, quando um novo nó é inserido no Grupo do Banco de Dados, um Mentor decidido pelo sistema de gerenciamento fica responsável por atualizá-lo, inserindo-o no contexto do _Group Database_. O novo nó terá o estado _Promotable_  até receber e indexar todos os documentos vindos do Mentor.

Temos uma replicação _master-slave_ onde os dados são enviados de maneira assíncrona toda vez que um novo nó entrar no _cluster_ ou algum dado mudar no _Master_.

Assim fica possível escalar sistemas a nível de _clusters_ com simplicidade.
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjQyMzY1MDc5LC0yMTMzNzM4ODRdfQ==
-->