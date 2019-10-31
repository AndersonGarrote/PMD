# Arquitetura de Distribuição e Replicação de Dados
O RavenDB opera sobre *clusters* que providenciam redundância e disponibilidade dos dados. No contexto do RavenDB, *clusters* são um grupo de servidores denominados *nós* que podem estar em mais de uma máquina. Cada um desses *nós* possuem uma cópia completa do banco de dados localmente, incluindo os documentos e índices, e assim podendo realizar qualquer operação de busca e escrita de dados. Além dessas operações locais em cada *nó*, há também operações que impactam o *cluster* inteiro, sendo no caso operações de, por exemplo, criação de documento. Com essa estrutura, o RavenDB pode ser dividido em duas camadas de funcionamento: **Camada de Cluster** e **Camada de Banco de Dados**.
A **Camada de Cluster** é composta por nós (3 ou mais, é recomendado um número ímpar) que realizam operações e se comunicam a partir de um protocolo de consenso próprio da RavenDB (chamado de Consenso *Rachis*, uma implementação derivada do protocolo Raft). Esse protocolo define um nó líder responsável por escolher o melhor nó para um determinado cliente, dando preferência a consistência das operações. 
A **Camada de Banco de Dados** representa os nós de um *cluster* que trabalham em união e cooperativamente e também grupos desses nós. A quantidade de membros nos grupos é definido pelo Fator de Replicação. Cada nó possui uma cópia completa da topologia do *cluster* (informações dos nós que compõe o cluster), no qual especifica qual nó possui um determinado banco de dados. Esse processo de replicação ocorre sobre uma conexão TCP entre os nós.
Essa distinção é importante para manter várias propriedades ao banco de dados. A eleição de um nó líder pelo consenso *Rachis* oferece a consistência forte, permitindo a continuidade da operação com a garantia do líder de que a maioria dos nós estão funcionando. Isso também significa que cada operação do *cluster* será futuramente aceito ou não pelo *cluster* inteiro. 
De acordo com o **Teorema CAP**, o *RavenDB* consegue ser **tolerante a partições**, **consistênte** e **disponível**. Mesmo contradizendo o teorema CAP, isso é possível pois ele aborda cada propriedade em uma camada diferente. A camada de *cluster* é  CP, ou seja, consistente mas pode não estar disponível. A camada de *banco de dados* é AP, ou seja, sempre disponível mas pode não estar consistente.

## Consistências
No *RavenDB*, a camada do banco de dados é replicado em múltiplos nós, compondo um grupo do banco de dados com tamanho determinado pelo Fator de Replicação. Os documentos em cada nó se mantém sincronizado a partir de replicação *master-master*, ou seja, todo nó possui uma cópia do banco de dados de seu grupo e a cada mudança em um documento é replicada automaticamente a outras instâncias do banco de dados. Toda a mudança nos documentos são mantidas de acordo com o *Change Vector*, que é a implementação no RavenDB do conceito de *vector clock* (Vetor de Relógio)
	- Quórum de consenso ( garantia de execução de tarefas em pelo menos (n/2) + 1 nós )

## Disponibilidade
text
	- Todo nó possui uma cópia do database
	- Isso, mais a consistência, permite que reads e writes ainda sejam processados contanto que pelo menos um nó esteja live.

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE4NDQyMzYwMiw2MDEwMzg1NjYsNDkxMD
M4MzMsNjAxMDM4NTY2LC0xNTUyODA2MDYwLC0zNzU0ODczMTBd
fQ==
-->