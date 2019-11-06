
## Consistências
A consistência é mantida na camada de *cluster* pois toda operação feita nesta camada precisa de um consenso, significando que a operação deve ser aceita de acordo com um quórum mínimo dos nós (n / 2  + 1 nós) ou ela não será registrada. Para isso, foi implementado o algoritmo de consenso Rachis*Toda a mudança nos documentos são mantidas de acordo com o *Change Vector*, que é a implementação no RavenDB do conceito de *vector clock* (Vetor de Relógio).


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MzQwMDMzNTMsLTE0OTE1OTQzNDAsLT
Q2Nzg5NDUsLTE2MTAxMDYyNSwtMTQ5MTUxNjAzOSwtMTY4MDY5
MjI2NiwxNzgzNTExNjI4LC03NzgxMzM4ODQsLTI4NzAwMzE3NF
19
-->