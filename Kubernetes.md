minikube (roda sob uma maquina virtual) - https://kind.sigs.k8s.io/docs/user/quick-start/ 
kind (roda com container docker) 

-> Instalar Kind 
-> Instalar Kubectl

Dica: docker start <nome do container || id do container>

-> Criando cluster:
------------------- 
kind create cluster

-> Acessando cluster 'kind-kind': 
---------------------------------
kubectl cluster-info --context kind-kind

* cat ~/.kube/
* docker ps 

-> Listar clusters kubernetes:
------------------------------
kubectl get nodes 


kind get clusters 

kind delete clusters kind 


-> Criar arquivo .yaml
----------------------

kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4

nodes: 
- role: control-plane
- role: worker 
- role: worker 
- role: worker

Criandro cluster com múltiplos nós:
-----------------------------------
kind create cluster --config=kind.yaml --name=bb9leko


Saber quais outros clusteres estão disponíveis para mudar o contexto (* cat ~/.kube/  )
---------------------------------------------------------------------------------------
kubectl config get-clusters

Mudando contexto do cluster 
---------------------------
kubectl config use-context {nome_do_cluster} 


==============================================================

K8S 
---
Necessidades: 
- Variáveis de Ambiente 
- Gerenciamento de Senhas /Secrets 
- Escolher os recursos computacionais que a minha aplicação roda 
- Health Check 
- Load Balacing 
- SSL / TLS 
- Domínio(www) -> Determinado Serviço 
- Estratégias de deploy (Blue/Green, Canary, etc) 
- Storage 

=> 
