
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
eyJoaXN0b3J5IjpbLTg3Nzg3NjU2MywtMTc3ODIzODI0MCwtOD
c3ODc2NTYzLC0xOTEzNzA5MDY2LDE4MjkzNTg4MTMsLTEzMzU2
MDA2MSwtMTA0NzU0OTE0OCwxNTYyNjYxNjYxLDczMDk5ODExNl
19
-->