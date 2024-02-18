Download Link .tar.gz
---------------------
wget https://go.dev/dl/go1.22.0.linux-386.tar.gz

Extraindo .tar.gz
-----------------
sudo tar -xvf go1.22.0.linux-386.tar.gz

Adicionando .bashrc ou .zshrc
-----------------------------
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH

GO
==

Iniciando módulo Go:
--------------------
go mod init github.com/bb9leko/apiRest-go-alura

Executando programa Go:
-----------------------
go run main.go 



Biblioteca
----------
Gorilla Mux: https://github.com/gorilla/mux

- go get -u github.com/gorilla/mux


Banco de Dados (Postgres - docker-compose.yaml) 
- adicionar servidor no pgadmin
- para pegar o host do postgres que está no container docker 

     Entrando no container docker: docker-compose exec postgres sh / docker inspect {id_container} | grep IPAddress
     Descobrindo ip: hostname -i 

	 