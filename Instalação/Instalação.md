## Instalando o RavenDB
>Observação: Este tutorial foi contruído baseado na versão estável 4.2.4 do RavenDB

O banco de dados de documentos NoSQL **RavenDB** pode ser baixado na seção de downloads do site: [ravendb.net/download](https://ravendb.net/download).

![página de downloads](https://github.com/AndersonGarrote/PMD/blob/master/Instala%C3%A7%C3%A3o/downloads_page.png?raw=true)



## sando o Docker
Caso deseje usar apenas uma máquina para seguir este tutorial, utilizaremos a versão para Docker, por ser multiplataforma e permitir realizar os testes de instâncias de nós no cluster usando containers.

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
	docker run -d -p 8080:8080 -p 38888:38888  ravendb/ravendb
``

## Versão Windows
Depois de baixar o arquivo .zip, extraia o conteúdo e execute o arquivo `run.psi` via linha de comando no prompt

## Versão Linux
Depois de baixar o arquivo .zip, extraia o conteúdo e execute o arquivo `run.sh` via linha de comando no prompt

``
	./run.sh
``
## Verificando estado do servidor

Podemos conferir o estado usando o cliente do browser, no endereço http://localhost:8080. A seguinte tela deve aparecer:

![cliente RavenDB](https://github.com/AndersonGarrote/PMD/blob/master/Instala%C3%A7%C3%A3o/telaraven.png?raw=true)


Neste ponto, podemos seguir para a **Configuração do Cluster**.


Fonte: https://ravendb.net

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMDI1MzE4MDAsLTE1NzQxNTMwODMsLT
MwMjM0Nzk4Miw4MjA4MDQ2NjMsLTYzNzIyMDc2MiwtMTE0MDYw
MzIwMSwxMjI3NDcwNDkxLDE1MDIwMDM2MzgsMTMxMzU4NDg3NS
wtMjcxNTkxMTIxLC0yMDA2ODc4NzAsNzI2Njg4NzcyLDM2NDkx
MzkwMywxNTgxNzU3OTgyLDEwNjMzNTg4NzksOTAyMTkyMDM1XX
0=
-->