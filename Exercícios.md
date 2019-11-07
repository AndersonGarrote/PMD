
1 - Retorne o primeiro nome de todos os empregados
	R.: `from Employees select FirstName`
2 - Retorne o nome das empresas localizadas n ail
	R.: `from Companies where Address.Cselect Name`
3 - Retorne e de  nmeo eereço das empresas localizadas no Bras
ila cidade de Campinas ou São Paulo
	R.: `from Companies 
where (Address.City = "Campinas" or Address.City = "Sao Paulo")
ountry = "Brazil" select Name, Address`

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg3Nzg3NjU2MywtMTkxMzcwOTA2NiwxOD
I5MzU4ODEzLC0xMzM1NjAwNjEsLTEwNDc1NDkxNDgsMTU2MjY2
MTY2MSw3MzA5OTgxMTZdfQ==
-->