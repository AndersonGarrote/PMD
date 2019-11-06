# Arquitetura de Distribuição
O RavenDB opera sobre *clusters* que providenciam redundância e disponibilidade dos dados. No contexto do RavenDB, *clusters* são um grupo de servidores denominados *nós*, que podem estar em mais de uma máquina. O RavenDB possui uma divisão de duas camadas de funcionamento: **Camada de Cluster** e **Camada de Banco de Dados**.
A **Camada de Cluster** é composta por nós (3 ou mais, é recomendado um número ímpar) que realizam operações de acordo com o consenso de todos os nós. Esse protocolo é um algoritmo de consenso desenvolvido para o RavenDB (chamado de Consenso *Rachis*, uma implementação derivada do protocolo Raft), e ele define um nó líder responsável por escolher o melhor nó para um determinado cliente, dando preferência a consistência das operações. 
A **Camada de Banco de Dados** representa os nós de um *cluster* que trabalham em união e cooperativamente. A quantidade de membros nos grupos é definido pelo Fator de Replicação. Cada nó possui uma cópia completa da topologia do *cluster* (informações dos nós que compõe o cluster), no qual especifica qual nó possui um determinado banco de dados. Esse processo de replicação ocorre sobre uma conexão TCP entre os nós.
Essa distinção é importante para manter várias propriedades ao banco de dados. A eleição de um nó líder pelo consenso *Rachis* oferece a consistência forte, permitindo a continuidade da operação com a garantia do líder de que a maioria dos nós estão funcionando. Isso também significa que cada operação do *cluster* será futuramente aceito ou não pelo *cluster* inteiro. 
De acordo com o **Teorema CAP**, o *RavenDB* consegue ser **tolerante a partições**, **consistênte** e **disponível**. Mesmo contradizendo o teorema CAP, isso é possível pois ele aborda cada propriedade em uma camada diferente. A camada de *cluster* é  CP, ou seja, consistente mas pode não estar disponível. A camada de *banco de dados* é AP, ou seja, sempre disponível mas consegue ser consistente.

# Replicação de Dados
Cada um desses *nós* possuem uma cópia completa do banco de dados localmente, incluindo os documentos e índices, e assim podendo realizar qualquer operação de busca e escrita de dados. Além dessas operações locais em cada *nó*, há também operações que impactam o *cluster* inteiro, sendo no caso operações de, por exemplo, criação de documento.

## Disponibilidade
text
	- Todo nó possui uma cópia do database
	- Isso, mais a consistência, permite que reads e writes ainda sejam processados contanto que pelo menos um nó esteja live.

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAwNzIxMTA1MiwxNTQ5MTA5NTY1LDE0Nj
g1MzUyOTIsMTE4NDQyMzYwMiw2MDEwMzg1NjYsNDkxMDM4MzMs
NjAxMDM4NTY2LC0xNTUyODA2MDYwLC0zNzU0ODczMTBdfQ==
-->