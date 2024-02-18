https://github.com/codeedu/wsl2-docker-quickstart

-> Habilitação do WSL2 (componente do window) e subcomponente do Hyper-V
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

-> Instalar pacote de atualização WSL2

-->Versões linux que vamos instalando, estejam habilitadas para a versão 2 do WSL
wsl --set-default-version 2

--> Erro ao abrir o Ubuntu 
C:\Users\User\AppData\Local\Packages (na pasta Canonical do Ubuntu - clicar com botão direito do mouse > opções avançadas >
desabilitar compreensão automática) 

--> Usuário: Leandro ; Senha: root 

--> Para integrar o WSL 2 com o Ubuntu, entrar no Docker Desktop > Settings > Resources > habilitar a integração com o Linux > refresh/reply

---------------------------------------------------------------------------------------------------------------------------

--> pwd (pasta atual) , ls (listar) , cd .. (voltar diretório) , cd {diretório} (acessar diretório)  

--> cd /mnt/c (se desenvolver nesta pasta, perderá performance) ; desenvolver no home/{usuário}

--> no terminal, para copiar: cp {diretory origem} {diretorio destino} ou grafico do windows explorer digitar '\\wsl$'

--> Instalar no VSCode a extensão RemoteWSL

--> No powershell: wsl -l -v (status das instâncias 
--> wsl --shutdown (desligas as distribuições)
--> no gitbash(cat .wslconfig) (limitar utilização) 

------------------------------------------------------------------------------------------------------------------------------

git gitlab github

-->Backup: copiar arquivo 'ext4.vhdx' em C:\Users\User\AppData\Local\Packages\CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc\LocalState
(quando reinstalar o wsl2/ubuntu - criar mesmo usuário/senha)
 
--> vim .profile ( acrescentar no final do arquivo - export DOCKER_BUILDKIT=1 - para acelerar o wsl) 

--------------------------------------------------


docker ps: lista os containers que estão rodando 

docker run hello-world (no bash do linux, na pasta home/leandro) --> ele não encontrará o repositório e baixará um do DOCKER HUB 
(se não colocarmos nada depois de hello-world, o docker entende como hello-world:latest)


*entrypoint/command (shellscript, arquivo binário ...) / como o container é um  processo, precisamos de um comando para que ele fique rodando. 
 docker ps -a 

Iniciando com o Docker - Executando Ubuntu 
------------------------------------------
 docker run -it ubuntu bash (bash é o comando que vai ser executado no container que foi baixado(ubuntu)) (-it = -i -t (i = modo iterativo (atacha o terminal com o container) (-t = tty (digitar coisas no termnal))
 	 docker ps / docker ps -a
docker start { id ou nome do container} 

 CONTAINER É UM PROCESSO
------------------------- 
 docker run -it --rm ubuntu:latest bash (--rm : quando sair do ubunto/container, o processo é removido)
(Comandos: uname -a)
Iniciando com bind mounts (Montando uma pasta do nosso computador, em um container) 
 Quando matamos um container, todo conteúdo é perdido, para isso existe a solução de Bind Mount (montar um volume no seu computador, e jogar seu conteúdo para o container. 
Criar uma pasta no computador local (Ex: html/index.html)
docker run -d --name nginx -p 8080:80 -v ~/Projects/fullcycle2/docker/html/:/usr/share/nginx/html nginx (-v: monta um volume) (monta a pastar que está no computador pra dentro do container, onde está o arquivo) (comando funcionou no PowerShell)
outra forma: docker run -d --name nginx -p 8080:80 --mount type=bind, source=”$(pwd)”/html,target=/usr/share/nginx/html nginx 
docker rm -f nginx (remover container) 
Diferença -v e --mount (-v cria pasta não existente, --mount da erro) 

Trabalhando com Volumes
-----------------------
 docker volume 
 docker volume ls 
Criar volume e apontar para um container docker e podemos compartilhar esse volume entre outro containers. 
 docker volume create meuvolume  --> docker volume inspect meuvolume (mountpoin: pasta em que os arquivo ficam criados em meu computador) 
 docker run --name nginx -d --mount type=volume,source=meuvolume,target=/app nginx 
 docker exec -it nginx bash (depois: cd /app/  -- > ls --> touch oi --> ls 
 docker run --name nginx2 -d --mount type=volume,source=meuvolume,target=/app nginx
 docker exec -it nginx2 bash (depois: cd /app/ --> ls --> touch oi2.txt) (estamos compartilhando o mesmo volume com o nginx e nginx2) 
 outra forma: docker run --name  nginx3 -d -v meuvolume:/app nginx 
 dock exec -it nginx3 bash (depois: cd /app/ --> ls) 
 docker volume prune (remove o que não está sendo utilizado) 
