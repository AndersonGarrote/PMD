# Segurança
No modo de desenvolvimento, o RavenDB roda no modo inseguro, porém em estágio de desenvolvimento é interessante a utilização do modo seguro, onde, por padrão somente o 
`localhost` está autendicado, desta forma, otros usuários terão que ser previamente autenticados para poderem acessar remotamente. O RavenDB  usa certificados de cliente `X509` para autenticação.

RavenDB oferece criptografia completa do banco e dados usando a bibliotaca _libsodium_.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjg4NjE4Njg1XX0=
-->