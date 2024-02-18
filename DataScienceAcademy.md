SQL para DataScience (15/05/2024)
=================================

#Capitulos 
[x]Introdução 

SQL 
=== 
https://db-engines.com/en/ranking

SGBD MySQL 
     GoogleDataStudio 
	 
- Carga no banco de dados 
  - setar path no windows (C:\Program Files\MySQL\MySQL Server 8.0\bin) 
  - para logar no mysql via terminal: 
      mysql --local-infile=1 -u root -p
  - privilégio para carga de dados via linha de comando: 
      SET GLOBAL local_infile=true;   
  
* Schema = BD ( Um BD pode ter vários schemas) 


========================================================================>

DSA 
---
https://www.w3resource.com/
dados.gov.br

- SGBD: Sistema Gerenciador de Banco de Dados
- Banco de Dados: Arquivos que armazenam os dados
- Banco de Dados Relacional: Armazenam os dados de forma relacional, onde os dados são distribuídos em tabelas que se relacionam 
- Modelo Relacional Lógico: Modelo que determina como os dados se relacionam (entidades, relacionamentos, cardinalidade) => Arquiteto de dados, Administrador de Dados 
- Modelo Relacional Físico: Instruções SQL que criam o modelo de dados relacional 


Python 
------
1) Ciclo de Vida da Análise de Dados 
Problema de Negócio > Preparação de Dados > Análise Exploratória > Visualização de Dados > Ações 

2) Análise de Dados X Ciência de Dados / Data Analytics X Business Analytics 

3)Tipos de Dados: 
------------------
-> Referente aos tipos de dados, podem ser: 
    1 - Armazenados na Memória: numéricos ou categóricos 
    2 - Fonte de Dados: primários ou secundários 
    3 - Linguagem de Programação: primitivos ou não primitivos 
    4 - Independente dos anteriores: estruturados, não estruturados ou semi estruturados


-> Dados Primários: Dados obtidos de geração própria,da própria empresa ou própria pesquisa. São dados captados 
no CRM, nas redes sociais, no site da própria empresa, por exemplo. Tudo aquilo que é de domínio próprio da
organização. 

-> Dados Secundários: São dados não próprios, de uma segunda fonte externa, mas que tem uma característica
importante do dados não ser público. O dados que se obtém de forma secundária não pode ser adquirido 
livremente por qualquer empresa. É o caso de parcerias de troca de dados entre empresas, que muitas vezes 
estão em setores complementares, mas não são concorrentes. 

-> Dados Terciários: São também dados externos, não próprios, mas esses sim públicos. Qualquer outras empresa
pode ter acesso, de forma paga ou gratuita. Hoje muitas empresas fazem coleta, armazenamento e enriquecimento 
de dados públicos para serem comercializados livremente no mercado. 

-> Dados Estruturados: São aqueles que têm uma classificação e uma lógica formal na maneira como são 
esquematizados. Aqui estamos falando de dados em um banco de dados, com linhas e colunas ou mesmo em uma 
planilha do excel. Dados estruturados são dados tabulares com estrutura bem definida. 

->Dados não Estruturados: São os dados estruturalmente mais brutos, capturados sem classificação ou esquema 
formal. São dados como posts em redes sociais, imagens, vídeos, e-mails, etc. Apesar de serem, sem dúvida, 
os dados mais abundantes que existem, eles requerem um grande trabalho - estratégico e operacional - 
para poderem ser utilizados de maneira útil no ciclo de análise de dados. 
]
-> Dados Semi-Estruturados: São dados igualmente sem uma organização esquemática, mas aqui já classificados
de alguma forma. Isso significa que há como saber como os dados estão separados, mas algum trabalho de 
estruturação deverá ser feito. Um bom exemplo são arquivos XML e JSON muitos usados em aplicações WEB.

-> Metadados: São aqueles dados que fornecem informações sobre outros dados. Um exemplo fácil do dia a dia 
está no nosso computador. Quando vemos o tamanho de um arquivos, sua extensão, a data de criação ou de 
modificação, são todos metadados que dão informação sobre um documento que em si já carrega uma série de dados 
desestruturados nesse caso). Metadados são dados sobre dados.  

4) Tipos de Variáveis:  

- Numéricos X Categóricos 

4.1) Qualitativas(Não Numéricas): 
        - Nominal (Profissão, Sexo, Religião) 
        - Ordinal (Escolaridade, Estágio da Doença, Classe Social) 

4.2) Quantitativas(Numéricas): 
        - Discreta (Num Filhos, Num de Acessos) 
        - Contínua (Altura, Salário, Peso) 




Estruturas de Dados 
-------------------
Dados: Primitivos X Não Primitivos 

Primitivos: Integer, Float, String, Boolean  

Não-Primitivos: 
 - BuiltIn: List, Tuple, Set, Dictionay  
 - UserDefined: Stack, Queue, Tree, Graph 
 
 
 
 
# Modelo Lógico - Modelo lógico que determina como os dados se relacionam (arquiteto ou administrador de dados) 
1.Entidades, relacionamentos, cardionalidades 

# Modelo Relacional Físico - Instruções SQL que criam o modelo no banco de dados relacional 

# Consulta, Filtro, Ordenação e Operadores 

*dados.gov.br 



Problema de Negócio 
Preparação de Dados 
Análise Exploratória 
Visualização de Dados 
Ações 


 python -m venv PyVenv
.\PyVenv\Scripts\activate.bat

-----------------------------------------

Iniciar servidor python: python -m http.server (cmd) 

No conda cli: 

variavel = {link} 
import requests 
resultado = requests.get(pagina) 
print(resultar)
type(resultado) 
resulta.status_code 
resultar.content[:15]
type(resultado.conteudo) 
fonte = resultar.text
type(fonte)