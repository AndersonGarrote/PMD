# Exercícios
- 1 - Retorne o primeiro nome de todos os empregados. ro Eseesslcirs
 - Retorne o nome das empresas localizadas noasil. ompaies ere dreeet e
 - Retorne o nome e o endereço  epea calaas na ciade d Cpa o o aloR fomCompanies e dres  minas or dress  o al
C nr  r eect Address`
4 - Retorne os pedidos com o preço do Frete (Freight) entre 50 e 100.
- `from Orders
where Freight BETWEEN 50 and 100`
5 - Retorne o nome dos produtos de um pedido e o endereço em que o pedido foi enviado. (Dica: Algumas colunas não são visíveis por padrão, selecione em Display as colunas para serem exibidas)
- `from Orders
select ShipTo, Lines[].ProductName as Products`
6 - Retorne os produtos e o preço total dos pedidos. (Dica: Declare função)
- `declare function lineItemPrice(l) {
    return l.PricePerUnit * l.Quantity * (1 - l.Discount);
}
from Orders as o
select {
    TopProducts: o.Lines
    Total: o.Lines.reduce((acc, l) => acc + lineItemPrice(l), 0)
}`
7 - Retorne os pedidos feitos pela empresa de ID 'companies/88-A'. Exiba o nome da empresa e o nome do funcionário. (Dica: `Use load`)
- `from Orders as o
where Company = 'companies/88-A'
load o.Employee as e, o.Company as c, o.Lines[].Product as products[]
select { 
    CompanyName: c.Name,
    EmployeeName: e.FirstName + " " + e.LastName,
    Products: products
}`
8 - Retorne o nome das empresas em ordem alfabética.
- `from Companies
order by Name as asc`
9 - Retorne os produtos em ordem decrescente do preço por unidade.
- `from Products 
order by PricePerUnit as double desc`
10 - Retorne as empresas localizadas a 500Km do Rio de Janeiro (Dica: Use as coordenadas Latitude -22 e Longitude -43)
- `from Companies
where spatial.within(
    spatial.point(Address.Location.Latitude, Address.Location.Longitude), 
    spatial.circle(500, -22.9306303, -43.358808, 'kilometers'))`
11 - Retorne os fornecedores que fornecem 3 ou mais produtos. Exiba o ID do fornecedor e o número de produtos.
`from Products
group by Supplier
where count() >= 3
select Supplier, count()`
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg0ODM3MTA3NywxMjg4NjgyNzY5LC04Nz
c4NzY1NjMsLTE3NzgyMzgyNDAsLTg3Nzg3NjU2MywtMTkxMzcw
OTA2NiwxODI5MzU4ODEzLC0xMzM1NjAwNjEsLTEwNDc1NDkxND
gsMTU2MjY2MTY2MSw3MzA5OTgxMTZdfQ==
-->