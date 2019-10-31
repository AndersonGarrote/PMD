
## Consistências
No *RavenDB*, a camada do banco de dados é replicado em múltiplos nós, compondo um grupo do banco de dados com tamanho determinado pelo Fator de Replicação. Os documentos em cada nó se mantém sincronizado a partir de replicação *master-master*, ou seja, todo nó possui uma cópia do banco de dados de seu grupo e a cada mudança em um documento é replicada automaticamente a outras instâncias do banco de dados. Toda a mudança nos documentos são mantidas de acordo com o *Change Vector*, que é a implementação no RavenDB do conceito de *vector clock* (Vetor de Relógio)
	- Quórum de consenso ( garantia de execução de tarefas em pelo menos (n/2) + 1 nós )


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc3ODEzMzg4NCwtMjg3MDAzMTc0XX0=
-->