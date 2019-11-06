
## Consistências
A consistência é mantida na camada de *cluster* pois toda operação feita nesta camada precisa de um consenso, significando que a operação deve ser aceita de acordo com um quórum mínimo dos nós (n / 2  + 1 nós) ou ela não será registrada. Para isso, foi implementado o algoritmo de consenso *Rachis*.  Na camada de banco de dados,  cada banco de dados é replicado para vários nós de um *cluster*, e os nós com o mesmo banco de dados forma um grupo. Todas as mudanças em documentos de um banco de dados são mantidas de acordo com o *Change Vector*, que é a implementação no RavenDB do conceito de *vector clock* (Vetor de Relógio).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA0MTAyMTE1NCw2NTQ4NjA0MzIsLTEyMj
kwOTk4NDYsLTE0OTE1OTQzNDAsLTQ2Nzg5NDUsLTE2MTAxMDYy
NSwtMTQ5MTUxNjAzOSwtMTY4MDY5MjI2NiwxNzgzNTExNjI4LC
03NzgxMzM4ODQsLTI4NzAwMzE3NF19
-->