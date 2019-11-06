
## Consistências
A consistência é mantida na camada de *cluster*, em que toda operação feita nesta camada precisa de um consenso, significando que a operação deve ser aceita de acordo com um por mais da metade dos nós ou ela não será registrada. Para isso, foi implementado o algoritmo de consenso RachisToda a mudança nos documentos são mantidas de acordo com o *Change Vector*, que é a implementação no RavenDB do conceito de *vector clock* (Vetor de Relógio).


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzI4MjgxODI3LC0xNDkxNTk0MzQwLC00Nj
c4OTQ1LC0xNjEwMTA2MjUsLTE0OTE1MTYwMzksLTE2ODA2OTIy
NjYsMTc4MzUxMTYyOCwtNzc4MTMzODg0LC0yODcwMDMxNzRdfQ
==
-->