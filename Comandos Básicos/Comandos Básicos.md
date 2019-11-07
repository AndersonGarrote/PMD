# Conceitos e comandos e xo básicos
[RQL](https://ravendb.net/docs/article-page/4.2/csharp/indexes/querying/what-is-rql)

Cláusula `from`
RQL: `from <collection>`
Exemplo:
RQL: `from Employees`
SQL: `select * from Employees`

Cláusula `where`
RQL: `where <operation>`
Exemplo:
RQL: `from Products where PricePerUnit = 15`
SQL: `select * from Products where PricePerUnit = 15`

Cláusula `select`
RQL: `select <column>`
Exemplo:
RQL: `from Products where PricePerUnit = 15 select Name`
SQL: `select Name from Products where PricePerUnit = 15`

Cláusula `order by`
RQL: `select <column>`
Exemplo:
RQL: `from Products where PricePerUnit = 15 select Name`
SQL: `select Name from Products where PricePerUnit = 15`

Saiba mais sobre RQL em: https://ravendb.net/docs/article-page/4.2/csharp/indexes/querying/what-is-rql
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg1NTM2MzU1LC0yMDU3OTA1MzE5LC02Nz
c3MDY0NDddfQ==
-->