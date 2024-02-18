React Native 
============

Cursos
======
202332 - React Native:Criando um Menu e Navegando entre telas (Orgshook com ReactNative)

repoGit: https://github.com/alura-cursos/react-native-navegacao-entre-telas/tree/Aula2
	   
			Tipos de navegação:

			1) Empilhada ou stack: o primeiro tipo de navegação, bastante utilizado em aplicativos, envolve uma sequência de telas que vão sendo “empilhadas”, ou seja, armazenadas 
			na memória do app, permitindo que o usuário retorne para uma tela anterior.

			2) Aba ou tab: o segundo tipo de navegação de aba ou tab é o mais simples de programar, por isso vamos começar nossos estudos por ele. A princípio, a navegação por tab 
			não permite voltar para uma tela anterior, mas sim mudar de tela criando dois ou mais contextos de navegação.

			3) Menu lateral ou drawer: o tipo de navegação drawer abre um menu lateral, permitindo a navegação para outras telas a partir desse menu. A princípio, a navegação drawer,
			também, não permite voltar para uma tela anterior. E também é muito semelhante a navegação por abas, pois permite a criação de contextos diferentes.

			4) Deeplink: os deeplinks são, literalmente, links que permitem o acesso para a aplicação de fora do app. Um exemplo disso é quando recebemos uma notificação de cupom, 
			em um app de delivery, que nos leva diretamente para uma tela em que há uma promoção.
	   
	   
	   
			  Biblioteca React-Navigation
	          - npm install @react-navigation/native 
			  - npm install react-native-screens react-native-safe-area-context
			  
			  Tab Navigation 
			  - npm install @react-navigation/bottom-tabs
			  

202255 - React Native: criando um app - 10 hrs (OrgHooks com Expo) 

201854 - React Native com Expo: navegação com menu e suporte às telas (gatito) 

202307 - React Native: Utilizando e Criando Hooks (OrgHooks com React CLI) 

 - ComponentDidMount() - Chamar uma função específica 
 - UseEffect() - Chamar uma função
 
 
Mobile 
======
ReactNative
===========

=> Expo vs React Native CLI  
---------------------------
 Expo
 ----
 - Limitações
 - Maior  
 - Não é necessário efetuar configurações nativas (IOs / Android) 
 
 
=>Conceitos
-----------
- hooks (estado, efeito e customizado)
- navegação entre telas
- flatlist 

*JSX - JavaScript e XML 


=> Cli ReactNative:
===================

Criar Projeto:
--------------
npx react-native init orgsHooks version 0.65.1

Rodar Projeto:
--------------
npx react-native start

npx react-native run-android

npm run android 



=> Expo CLI:
============

Instalando ExpoCLI:
-------------------
npm install -g expo-cli (Depreciado) 

Criar Projeto com ExpoCLI:
----------------------------
expo init {nome_projeto} 

npx create-expo-app AwesomeProject

* TypeScript -> renomear arquivo app.js -> app.tsx

Rodar Expo:
-----------
expo start 

Instalando Font CLI 
-------------------
expo install expo-font @expo-google-fonts/

Links 
-----

APIs Públicas:
https://rapidapi.com/hub
https://github.com/public-apis/public-apis

Simulador FakeAPI:
https://github.com/typicode/json-server

Prótipo mocks: 
https://www.figma.com/file/xEHiFcNLsIEKdostk64RRZ/Ficando-Online---Design?type=design&node-id=0-1&mode=design

Configurando Ambiente React Native:
-----------------------------------
https://www.alura.com.br/artigos/configurando-o-ambiente-react-native?_gl=1*hyjw19*_ga*MTM0OTI2Nzc4MS4xNjkwNjU5MjQ2*_ga_1EPWSW3PCS*MTY5MjEzNjIyMi4xMC4xLjE2OTIxNDA5NzAuMC4wLjA.*_fplc*Z2JTYXdVOWp3RTY5bTkzSk9WOWk4Z3dHRXMlMkZwYXFQelp5N0oyZ1hKajczMTRVZUpkUnBCaFJUVFFHYnM2aUpHVEZhY1FDemp4aGNuNG42UW9vWVpERmMlMkZ4Rmhpblg0S2I3ZW9sd1RNWUd2JTJGblpUZnV3Y1RVa29IeTdXUnZ3JTNEJTNE*_ga_59FP0KYKSM*MTY5MjEzNjIyMi4xMS4xLjE2OTIxNDA5NzAuMC4wLjA.

Migração Expo para React Native: 
--------------------------------
https://www.alura.com.br/artigos/como-fazer-a-migracao-do-expo-para-react-native-cli?_gl=1*1ufi4wa*_ga*MTM0OTI2Nzc4MS4xNjkwNjU5MjQ2*_ga_1EPWSW3PCS*MTY5MjEzNjIyMi4xMC4xLjE2OTIxNDEzNzUuMC4wLjA.*_fplc*cTk5cWZOWm8lMkJiVW9DMElsZ3d2ZVg2NVVLRUZEc0YyZWVXSWw3U0pBZ29acTU0MWRQajYlMkJXelc4NUJzaERKb2YwUlA1dXNoMlp2S2IlMkZjZnAxelJyV0RucXlqSExwM0NaNHpIMFFaeGo3bzIyJTJGVXZLQTglMkJZVUZUcnllb1RJZyUzRCUzRA..*_ga_59FP0KYKSM*MTY5MjEzNjIyMi4xMS4xLjE2OTIxNDEzNzUuMC4wLjA.






React Native 
------------

NativeBase - Biblioteca para gerar componentes, tanto React como React Native 


=================================================================================================


203091 - React Native - Integrando um APP a uma web API

repoGit: https://github.com/alura-cursos/react-native-ficando-online/blob/aula2/src/servicos/api.js

Axios - biblioeteca javaScript para requisições HTTP  (pode ser usar o 'fetch' do próprio JS) 
https://github.com/axios/axios
-Trata o formato de retorno dos dados 
-Trata erros de requisição 

npm install axios@0.26.0


export default function App() {

    useEffect(() => {
        async function pegarDados(){

        }
    }, [])
	
	
	

202368 - React Native: utilizando Web API 


FakeAPI 
=======

Biblioteca para simular uma FakeAPI: json-server (https://github.com/typicode/json-server)

mockup = prototipo UX

npx json-server --{enderecoIP} teste.json



=================

Debugger
--------

https://reactnative.dev/docs/debugging?js-debugger=new-debugger#accessing-the-in-app-developer-menu

https://reactnative.dev/docs/other-debugging-methods