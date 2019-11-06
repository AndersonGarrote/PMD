## Transações
As operações no RavenDB sobre documentos e em armazenamentos feitas são todas ACID:
 - Atômico: Toda operação é executada completamente, sem ser interrompido por outra operação.
 - Consistência: O estado de um documento se mantêm em toda a execução da operação.
 - Isolamento: Todas as operações em uma transação não interferem em outra transação.
 - Visibilidade: As transações em mais de um documento são disponíveis imediatamente após o registro. 
 - Durabilidade - Toda transação será executada no nó de banco de dados inteiro.
Na camada de *cluster*, as transações também são ACID:
 - Atômico: Garantia de execução da transação se for aprovado pelo quórum e pelo teste de simultaneidade, caso contrário a transação é desfeita.
 - Consistência: Se a transação for completa e os documentos estão sincronizados ao nós, então a requisição feita pelo nó será feita.
 - Isolamento: Não há interferência por outra transação durante as operações.
 - Durabilidade - Com a transação aceita.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEwNjEwODU3NCwzNjUzODcxOTQsLTI2MD
UyMTc3OF19
-->