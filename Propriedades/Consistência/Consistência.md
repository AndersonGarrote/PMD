
## Consistência
A consistência é mantida na camada de *cluster* pois toda operação feita nesta camada precisa de um consenso, significando que a operação deve ser aceita de acordo com um quórum mínimo dos nós (n / 2  + 1 nós) ou ela não será registrada. Para isso, foi implementado o algoritmo de consenso *Rachis*.  Na camada de banco de dados,  cada banco de dados é replicado para vários nós de um *cluster*, e os nós com o mesmo banco de dados forma um grupo. Todas as mudanças em documentos de um banco de dados são mantidas de acordo com o *Change Vector*, que é a implementação no RavenDB do conceito de *vector clock* (Vetor de Relógio).

Fontes: https://ravendb.net
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDQxMTU2NzM4LC0xNTI5MzIwNDkxLC03OD
MwNTExMzMsMjA0MTAyMTE1NCwtMTIyOTA5OTg0NiwtMTQ5MTU5
NDM0MCwtNDY3ODk0NSwtMTYxMDEwNjI1LC0xNDkxNTE2MDM5LC
0xNjgwNjkyMjY2LDE3ODM1MTE2MjgsLTc3ODEzMzg4NCwtMjg3
MDAzMTc0XX0=
-->