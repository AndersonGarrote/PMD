## Transações
As operações no RavenDB sobre documentos e em armazenamentos feitas são todas ACID:
 - Atômico: Toda operação é executada completamente, sem ser interrompido por outra operação.
 - Consistência: O estado de um documento se mantêm em toda a execução da operação
 - Isolamento: Todas as operações em uma transação não interferem em outra transação.
 - Visibilidade: As transações em mais de um documento são disponíveis imediatamente após o registro. 
 - Durabilidade - Toda transação será executada no nó de banco de dados inteiro.
Na camada de *cluster*, as transações também são ACID:
 - Atômico: Garantia de execução da transação se for aprovado de acordo com o quórum
 - Consistência: O estado de um documento se mantêm em toda a execução da operação
 - Isolamento: Todas as operações em uma transação não interferem em outra transação.
 - Durabilidade - Toda transação será executada no nó de banco de dados inteiro.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTcyNTI1ODkwMywzNjUzODcxOTQsLTI2MD
UyMTc3OF19
-->