Comunicação Entre Sistemas (Sistemas Distribuídos) 
==================================================
*Mensageria (Formas de Comunicação) 
-Rest (Níveis de Maturidade) => Stateless(sem guardar estado);
-Grpc 
-GraphQL 
-Sincrona(RequestResponse)XAssíncrona(pode ter dados inconscistentes) 

Soluções de Mensageria:Kafka, RabbitMQ, AmazonQs


REST:Níveis de Maturidade  
=========================
Nível 0: The swamp POX (Sem padronização) 
Nível 1: Utilização de Resources (trabalhar com substantivos através de verbos http)
Nível 2: Verbos HTTP 
Nível 3: HATEOAS: Hypermedia as The Engine of Application State (Responde o enpois e disponibiliza o que mais
podemos fazer (o que podemos fazer com outros recursos) 

=> Rest: HAL(_links, _embedded), Collection+JSON e Siren // (XML vs JSON)

=> Rest - HTTP Method Negotiation 
   -> Método options: permite informar quais métodos são permitidos ou não em determinado recurso. 

        - Content Negotiation (métido Accept Negotiation) 

RemoteContainer(VsCode) 
api-tools.getlaminas.org/download

gRPC (https://grpc.io/docs/languages/go/quickstart/)
====================================================

Instalando protocol compiler plugin 
-----------------------------------
$ go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
$ go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2