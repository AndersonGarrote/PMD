# Instalando o RavenDB

O banco de dados de documentos NoSQL **RavenDB** pode ser baixado na seção de downloads do site: [ravendb.net/download](https://ravendb.net/download).

## Usando o Docker
Para fins de demonstração deste tutorial, utilizaremos a versão para Docker, por ser multiplataforma e permitir realizar os testes de instâncias de nós no cluster usando containers.

>Para isso, é necessário instalar o docker, pelo instalador de programas do sistema operacional ou direto do site [www.docker.com](https://www.docker.com). Nesse endereço também é possível encontrar, mais informações úteis sobre o Docker.

Com o Docker instalado, escolheremos a respectiva versão no site do RavenDB, após aceitar os termos e condições. Seremos redirecionados para outra página, com diversas informações de configuração.
Estamos interessados no seguinte comando em um terminal:

``
	docker pull ravendb/ravendb
``

Assim, baixaremos a imagem com RavenDB para Docker.
> Pode ser necessário estar com um usuário administrador para realizar os comandos. No Linux, basta usar `sudo`  antes dos comandos do Docker.

Feito isso, podemos subir um container usando o seguinte comando:

``
	docker run -d -p 8080:8080  ravendb/ravendb
``

Podemos conferir o estado usando o cliente do browser, no endereço http://localhost:8080.

Neste ponto, podemos seguir para a **Configuração do Cluster**.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk0NTM4NDEwLDEzMTM1ODQ4NzUsLTI3MT
U5MTEyMSwtMjAwNjg3ODcwLDcyNjY4ODc3MiwzNjQ5MTM5MDMs
MTU4MTc1Nzk4MiwxMDYzMzU4ODc5LDkwMjE5MjAzNV19
-->