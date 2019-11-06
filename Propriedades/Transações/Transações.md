## Transações
As operações no RavenDB sobre documentos e em armazenamentos feitas são todas ACID:
 - Atômico: Toda operação é executada completamente, sem ser interrompido por outra operação.
 - Consistência: O estado de um documento se mantêm em toda a execução da operação
 - Isolamento: Todas as operações em uma transação não interferem em outra transação.
 - Visibilidade: As transações em mais de um documento são disponíveis imediatamente após o registro. 
 - Durabilidade - Toda transação será executada no nó de banco de dados inteiro.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MzQ5ODkzMjMsMzY1Mzg3MTk0LC0yNj
A1MjE3NzhdfQ==
-->