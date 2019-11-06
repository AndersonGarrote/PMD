
## Consistências
A consistência é mantida na camada de *cluster* pois toda operação feita nesta camada precisa de um consenso, significando que a operação deve ser aceita de acordo com um quórum mínimo dos nós (n / 2  + 1 nós) ou ela não será registrada. Para isso, foi implementado o algoritmo de consenso *Rachis*.  Na camada de banco de dados,  cada banco de dados é replicado para vários nós de um *cluster*, e os nós com o mesmo banco de dados forma um grupo. Toda a mudança nos documentos de um banco de dados são mantidas de acordo com o *Change Vector*, que é a implementação no RavenDB do conceito de *vector clock* (Vetor de Relógio).


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc3MzI5NzQ2NSwtMTQ5MTU5NDM0MCwtND
Y3ODk0NSwtMTYxMDEwNjI1LC0xNDkxNTE2MDM5LC0xNjgwNjky
MjY2LDE3ODM1MTE2MjgsLTc3ODEzMzg4NCwtMjg3MDAzMTc0XX
0=
-->