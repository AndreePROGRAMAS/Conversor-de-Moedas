# Conversor-de-Moedas
Aplicação que converte um determinado valor em reais para dolar e euro baseado na atual cotação

André Luiz Bueno e Gabriel Henrique de Souza, 3°DS, ETEC Euro Albino de Souza

O app consiste em um conversor de taxa de cambio que transorma a moeda brasileira (real) em seu valor equivalente em Dolar e em Euro. Sua primeira tela é a de login onde a entrada do usuário deverá ser feita com sua conta do google, ao clicar em "Entrar com Google" a função onGoogleSignIn é chamada, ela é responsavel por iniciar um fluxo de autenticação via google usando o useOAuth fornecido pelo Clerk, após  isso o usuario é redirecionado para a pagina de autenticação, caso o login seja bem-sucedido o fluxo retorna ao aplicativo e a sessão é ativada usando setActive tambem no clerk. A segunda tela é o convertor em si, o componente utiliza o useUser do clerk para acessar os dados do usuário autenticado, como nome e imagem de perfil, o botao sair realiza o logout por meio da função signOut. Para exibir a cotação e transformar determinados valores é utilizado á API ExchangeRate, ela acessa as cotações em tempo real e as armazena nas variaveis "cotacaoDolar" e "cotacaoEuro", a conversão é feita quando o usuário insere o valor, o mesmo fica armazenado na várivavel "valorReais", ao clicar em converter a função handleConversao é chamada, ela multiplica o valor digitado pelas taxas de câmbio para calcular os valores correspondentes em Dólar e Euro. Os valores convertidos são armazenados em valorDolar e valorEuro e exibidos na tela.

A aplicação é feita com React Native + expo (elementos que permitem de aplicativos para Android e iOS com um único código base). O clerk é utilizado na autenticação do usuário e 
 no fornecimento de dados como nome e imagem de perfil. Há também a integração com uma API externa que permite as conversões monetárias e o acesso as taxas de cambio atualizadas

Instruções: 
Primeiro passo: O usuário faz login com o Google pela tela de SignIn.
Segundo passo: Após o login, o usuário acessa a tela principal, onde pode:
Ver seu nome e foto.
Conferir as cotações atualizadas de Dólar e Euro.
Inserir um valor em Reais e convertê-lo para as outras moedas.
Logout: O usuário pode encerrar sua sessão a qualquer momento.

Requisitos do usuário:
Sistema operacional: Android ou IOS
Conexão com a Internet: Necessária para:
Fazer login com o Google.
Consultar as taxas de câmbio em tempo real.
Aplicativo Expo Go (se for distribuído no Expo): Caso você esteja testando no ambiente Expo.
Conta Google:
O usuário precisa ter uma conta Google válida para fazer login no aplicativo.

Requisitos para DEV:
Ferramentas e Configuração Inicial:
-Node.js (v14 ou superior).
-Expo CLI instalado globalmente (npm install -g expo-cli).
-Editor de código como Visual Studio Code.
Dependências do Projeto:
-React Native e Expo configurados.
Bibliotecas usadas no código:
-@clerk/clerk-expo (para autenticação).
-expo-web-browser (para gerenciar fluxos de autenticação OAuth).
-expo-linking (para redirecionamentos de URL).
-Outros componentes personalizados, como Button.

Versões utilizadas:
Expo: ~51.0.28
API: v4

fotos do app funcionando:
![image](https://github.com/user-attachments/assets/c415ead1-ff25-4ecd-8815-15e2cd73e831)
![image](https://github.com/user-attachments/assets/75e512e7-9dae-4dc2-b99f-2a8f80f35d8a)
![image](https://github.com/user-attachments/assets/5b9a43aa-bfa8-45b1-be47-83e87ae5119a)
![image](https://github.com/user-attachments/assets/f4a9c993-ec4d-46f7-86b9-596507008c51)

Passo a passo de instalação:

1. Instalar o Node.js
O Expo requer o Node.js para funcionar corretamente. Certifique-se de que está instalado na sua máquina.

Baixe e instale o Node.js. Recomenda-se a versão LTS.
Verifique se o Node.js e o npm estão instalados:


node --version
npm --version

2. Instalar o Expo CLI
No terminal, instale o Expo CLI globalmente:
npm install --global expo-cli

Verifique se a instalação foi bem-sucedida:
expo --version

3. Criar um Novo Projeto Expo
Se ainda não tiver um projeto, crie um novo:

expo init meu-projeto

Escolha o template desejado (por exemplo, "blank").

Navegue até a pasta do projeto:
cd meu-projeto

4. Instalar Dependências do Projeto

@clerk/clerk-expo
Para autenticação de usuários, incluindo suporte a OAuth (ex.: login com Google).
npm install @clerk/clerk-expo

expo-web-browser
Necessária para abrir fluxos de autenticação no navegador.
npm install expo-web-browser

expo-linking
Usada para redirecionamentos e criação de URLs dentro do app.
npm install expo-linking

5. Iniciar o Projeto Expo
Inicie o servidor de desenvolvimento do Expo:
expo start

Isso abrirá uma interface no navegador onde você pode:

-Escanear o QR Code com o app Expo Go no seu dispositivo móvel.
-Rodar o projeto em emuladores Android ou iOS, caso configurados.



