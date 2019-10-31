# Instalando o RavenDB

O banco de dados de documentos NoSQL **RavenDB** pode ser baixado na seção de downloads do site: https://ravendb.net/download.

Para fins de demonstração deste tutorial, utilizaremos a versão para Docker, por ser multiplataforma e permitir realizar os testes de instâncias de nós no cluster usando containers.

>Para isso, é necessário instalar o docker, pelo instalador de programas do sistema operacional ou direto do site: https://www.docker.com. Nesse endereço também é possível encontrar, mais informações úteis sobre o Docker.

Com o Docker instalado, escolheremos a respectiva versão no site do RavenDB, após aceitar os termos e condições. Seremos redirecionados para outra página, com diversas informações de configuração.
Estamos interessados no seguinte comando em um terminal:

``
	docker pull ravendb/ravendb
``

Assim, baixaremos a imagem com ravendb para Docker.

Feito isso, podemos subir um container usando o seguinte comando:

``
	docker run -d -p 8080:8080  ravendb/ravendb
``

Podendo ser acessado pel



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM0NDk5NDQyLC0yNzE1OTExMjEsLTIwMD
Y4Nzg3MCw3MjY2ODg3NzIsMzY0OTEzOTAzLDE1ODE3NTc5ODIs
MTA2MzM1ODg3OSw5MDIxOTIwMzVdfQ==
-->