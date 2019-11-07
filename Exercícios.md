
1 - Retorne o primeiro nome de todos os empregados
	R.: `from Employees select FirstName`
2- Retorne o nome das empresas localizadas no Brasil
	R.: `from Companies where Address.Country = "Brazil" select Name`
2- Retorne o nome e o endereço das empresas localizadas na cidade de Campinas ou São Paulo
	R.: `from Companies 
where (Address.City = "Campinas" or Address.City = "Sao Paulo")
select Name, Address `
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTcxMDIzNTI1MSwxODI5MzU4ODEzLC0xMz
M1NjAwNjEsLTEwNDc1NDkxNDgsMTU2MjY2MTY2MSw3MzA5OTgx
MTZdfQ==
-->