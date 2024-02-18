WSL
===

wsl -l -v

Criar imagem:
------------- 
wsl --export Ubuntu C:{Caminho no windows} 


GoLang
======

Iniciando módulo GoLang: 
------------------------
go mod init github.com/devfullcycle/goesquenta12

Rodando projeto: 
----------------
go run main.go

Build/Run:
----------
go build > go run ./goesquenta12 (GOOS=windows go build)

Eportando variável path:
------------------------
export PATH=$PATH:/usr/local/go/bin:~/go/bin 

????????????
------------
go mod tidy 


go > bin/pkg/src 


NestJs
======

Install CLI:
------------
npm install -g @nestjs/cli

Criar projeto Nest:
-------------------
nest new nestjs-api-rest
npx @nestjs/cli new {nomeProjeto} 

Rodando modo dev:
-----------------
npm run start:dev

Criando controllers(cli): 
-------------------------
nest g controller products

Criando services(cli):
----------------------
nest g service products

Gerando resouce (cli):
----------------------
nest g resource 

Prisma ORM:
-----------
npx prisma init  

??????
----------------------
npx prisma migrate dev 


dockerstop='docker stop $(docker ps -a -q)' 

SOLID
=====

- Single Responsibility - Devemos separar coisas que mudam por motivos diferentes (motivo de mudança significa responsabilidade) 
- Open/Closed - 
- Liskov Substitution
- Interface Segregation - 
- Dependency Inversion - High Level(Negócio) modules should not depend on low level modules (rede  

*Design OO ( Alta Coesão e Baixa Acoplamento)
*Reduz a Fragilidade
*Aumente Reuso
*Reduza Rigidez 

Patterns
========
Strategy
Repository 
DAO 


Integrando toda Aplicação
===============================

-> GoLang e Kafka 
   ==============
go run cmd/trade/main.go

-> Nest
   ====
npm install 
npm run start:dev
npx prisma generate (tipagens do prisma) 
npx prisma studio (localhost:5555)

npm install @nestjs/mongoose

-> Next
   === 
npm run dev  (porta Next 3000 - Nest 3001)
rm -rf .next
npm run dev

npm install swr 

npm install mongoose
npm install @types/mongoose --save-dev




((Server Server Events - Servidor enviar eventos para browser (http)) vs websockets 
->header(conexão de longo prazo)

http X http2 
       (Protocol Buffers -> Dados trafegados em formato binário 	
	  
Arquitetar > Entregar Testado > Deployada > Monitorada 

"Filas" 

SSE (Server sent Event)     vs  WebSockets(bidirecional) 

*comunicação unidirecional 

Meio de transporte - API REST, GraphQL, Microservice,WebSockets

DTO - Transferir dados entre duas camadas de um projeto

*Decorator 


[app_module] 
Módulos
Controller - Intermediário. Recebe as requisições, processa alguma coisa na área de negócio e devolve a resposta.
Providers 

service - Processamento de negócio [DDD, Arquitetura Hexagonal] (@Injectable) 

NestJS - Containers de Serviços 
         coc - convention over configuration
		 kebab case
		 
Prisma ORM  

NPM X NPX - Instala localmente vs instala itens externos 

=========================================================================================================================

WSL2 Tutorial - WesleyWilliam - FullStack/FullCycle:
----------------------------------------------------
https://github.com/codeedu/wsl2-docker-quickstart


Comandos: 
---------

Config: .wslconfig  
-------

ListVolumes: wsl -l -v 
------------

-----------------
|Comandos Docker|
-----------------

Listar Contairners: docker ps -a  
-------------------

Rodar Container com Imagem: docker run --name nginx nginx 
---------------------------

>Subir Container Nginx, detached, publicar na porta 8080:
--------------------------------------------------------
docker run --name nginx -d -p 8080:80 nginx  
-d: detachated 
-p: publish 
--name: nomear container 

>>Executar o shell do Nginx - Listar Diretórios:
------------------------------------------------
docker exec nginx ls 
exec: executa comandos dentro do container 
ls: lista os diretórios dentro do nginx 

>>Executar o shell do Nginx - Executar bash:
---------------------------------------------
docker exec -it nginx bash 
-it:iterative 

Remover Container:
------------------
docker rm nginx -f 
-f:force 


apt-get update 

apt-get install vim    

exit 

VIM:
----
I - Insert 
ESC - sair do modo Insert 
shift + : : W - Write 
:q : sair 
:wq : sair gravando 

-> Se o container morrer, você perde a alteração. Você não grava na imagem, a imagem é imutável. 

Bind Mount: Monta um volume dentro do seu computador para o container. Assim se o container morrer, o arquivo ainda está dentro do computador.
----------
docker run -d --name nginx -p 8080:80 -v 
-v: montar um volume ~/Projects/fullcycle2/docker/html/:/usr/share/nginx/html nginx  (montar Volume do computador no Volume do Container) *Cria a pasta caso esta não exista

(nova forma) docker run -d --name nginx -p 8080:80 --mount type=bind,source="$(pwd)"/html,targer=/usr/share/nginx/html nginx 

Volumes
--------

docker volume 

docker create volume {nome}

docker volume inspect {nome}

docker run --name nginx -d 8080:80 --mount type=volume,source=meuvolume,targer=/app nginx 

	docker -it nginx bash 

docker run --name nginx3 -d -v meuvolume:/app nginx 

docker volume prune 

Imagens (Container Registry)
============================

baixar uma imagem: docker pull ubuntu 
------------------

listar imagens: docker images 
--------------

docker rmi php:latest

docker build -t bb8leko/nginx-com-vim:latest .

docker images 

docker run -it bb8leko/nginx-com-vim bash

---------------------------
sudo systemctl daemon-reload
sudo chmod 666 /var/run/docker.sock
---------------------------
*Dockerfile

--------------------------------
docker ps -a -q 

docker rm $(docker ps -a -q) -f 
-------------------------------

docker run -rm bb8leko/hello

KAFKA
=====

docker-compose up -d 

docker-compose ps 

docker exec -it kafka_kafka_1 bash 

kafka-topics 

kafka-topics --create --topic=teste --bootstrap-server=

================================



----------------------------------------------------------------------------------------------------------------

Terraform(OpenSource) - Provisionar Infraestrutura, instalar serviços, configurações 
(Empresa - HashCorp) -Infra as Code (IaC) 
 => Camadas de abstração que permite trabalhar com vários providers: Kubernets, Aws
Provisionar Infra: Pegar os componentes da infra, e fazê-los que sejam criados no cloudprovider ou plataforma PaS