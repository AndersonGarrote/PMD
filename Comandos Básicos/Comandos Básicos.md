# Conceitos e comandos e básicos

Por ser um banco de dados NoSQL, alguns conceitos são diferentes se comparados com um RDBMS comum, mas podemos fazer um paralelo entra a nomenclatura de cada um deles: 


O RavenDB possí uma linguagem de consulta própria chamada [RQL](https://ravendb.net/docs/article-page/4.2/csharp/indexes/querying/what-is-rql), similar à SQL, mas com consultas escritas em uma ordem um pouco diferente.

## Exemplos de consultas 

### Cláusula `from`
RQL: `from <collection>`

- Exemplo:
Retornar todos os documentos da coleção Employees

RQL: `from Employees`

SQL: `select * from Employees`

### Cláusula `where`
RQL: `where <operation>`

- Exemplo:
Retornar todos os Produtos com preço por unidade = 15

RQL: `from Products where PricePerUnit = 15`

SQL: `select * from Products where PricePerUnit = 15`

### Cláusula `select`
RQL: `select <column>`

- Exemplo:
Retornar os nomes dos Produtos com preço por unidade = 15

RQL: `from Products where PricePerUnit = 15 select Name`

SQL: `select Name from Products where PricePerUnit = 15`

### Cláusula `order by`
RQL: `order by <column> as <DataType> <OrderingType>`

- Exemplo:
Retornar Produtos com preço por unidade = 15 ordenados pelas unidades em pedidos

RQL: `from Products where PricePerUnit = 15 order by UnitsOnOrder as long `

SQL: `select * from Products where PricePerUnit = 15 orderby UnitsOnOrder`

### Cláusula `group by`
RQL: `group by <column>`

- Exemplo:
Retornar Fornecedores com mais de 15 produtos

RQL: `from Products group by Supplier where count() > 15`

SQL: `select * from Products where count(Supplier) = 15 group by Supplier`

`

Saiba mais sobre RQL em: https://ravendb.net/docs/article-page/4.2/csharp/indexes/querying/what-is-rql
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzg3NDIyNzAzLDEwNjE3NTAxMDEsLTIwNT
c5MDUzMTksLTY3NzcwNjQ0N119
-->
