---------
|Quarkus|
--------- 
- Kubernetes
- Container First 
- Programação Imperativa e Reativa 
- Site Quarkus (GetStarted)

Instalar Extensões:
-------------------
./mvnw quarkus:add-extensions -Dextensions="hibernate-orm-panache"

./mvnw quarkus:add-extensions -Dextensions="quarkus-jdbc-postgresql"

./mvnw quarkus:add-extensions -Dextensions="quarkus-resteasy-jackson"

Extensões Retiradas: 
--------------------
    <dependency>
      <groupId>io.quarkus</groupId>
      <artifactId>quarkus-resteasy-reactive</artifactId>
    </dependency>

Criando Projeto Quarkus: 
------------------------
(CLI) quarkus create app com.github.bb9leko.ifood:ifood:0.0.1-SNAPSHOT
(MVN) mvn io.quarkus.platform:quarkus-maven-plugin:2.11.2.Final:create \
       -DprojectGroupId=org.acme \
       -DprojectArtifactId=getting-started \
       -Dextensions="resteasy-reactive"
     cd getting-started
(SITE)


https://nirisarri.github.io/2020-11-03-how-to-install-and-run-intellij-idea-for-linux-in-wsl2/


mvn clean package -DskipTests

mvn quarkus:add-extension -Dextensions="jdbc-postgres, orm-panache, resteasy-jsonb, openapi, hibernate-validator"

docker-compose up -d 

mvn quarkus:dev 


Keycloak - Gerenciamento de Acesso de Usuários (ou outras ferramentas para gerar o TokenJWT) 
- vamos usar microprofile jwt 


mvn quarkus:add-extension -Dextensions="jwt"
-application.properties  
-Chave pública: http://localhost:8180/auth/realms/ifood
-Login Keycloak: admin/admin 
-LoginOauth: propietario1 / 123456 / front-web-ifood

mvn quarkus:add-extension -Dextensions="metrics"


Quarkus - Keycloak 
-------------------
-Criar Realm 
-Criar Client (front-web-cadastro)
-Configurar Login 
-Criar User - propietario 
-Alterar Senha
-Criar Role no Realm: propietario 
-Vincular Role ao cliente 
-Entrar no client -> Mapper -> Add built in , realm roles, mapear groups 