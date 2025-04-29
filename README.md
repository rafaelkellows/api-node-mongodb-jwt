# Autenticação com Node.js e MongoDB com JWT - Login e Registro com Node.js
  
  ## 1. Instalações importantes 

  Antes de prosseguir, é necessário ter algumas instalações na sua maquina. Caso já tenha instalados, pule para a próxima etapa.

  ### 1.1 Node.js/NPM
  - Baixe o **Node.js** em https://nodejs.org/en/download e, após a instalação, execute o seguinte commando em algum terminal para verificar se a instalação foi bem sucedida.
    ### Verificar a versão do Node.js
    ```shell
    node -v
    ```
    ### Verificar a versão do NPM
    ```shell
    npm -v
    ```
  
  ### 1.2 MongoDB
  - Crie uma conta https://account.mongodb.com/account/login ou acesse usando a conta do Google.
  
  ### 1.3 Plataforma de API
  - Baixe/Instale o Postman em https://www.postman.com/, ou;
  - Baixe/Instale o Insomnia em https://insomnia.rest/download/.


  ## 2. O Projeto API
  
  Foi utilizado o VSCode como IDE para desenvolvimento. 

  ### 2.1 Configurando o Projeto 
  - Na pasta root do seu projeto, execute o seguinte commando:
    
    ```shell
    npm init -y
    ```
    Esse comando iniciará o projeto com node e criará um arquivo chamado package.json
  
  - A seguir, execute o seguinte commando para instalar as dependencias para o projeto

    ```shell
    npm install bcrypt dotenv express jsonwebtoken mongoose
    ```
    Esse comando instalará:
    - **crypt:** criará e decodificará a hash (senha) para acessos de usuário
    - **dotenv:** arquivo de configuração da maquina. Geralmente não versionado.
    - **express:** framework front e backend juntos
    - **jsonwebtoken:** para manusear o token
    - **mongoose:** banco de dados

  - A seguir, execute o seguinte commando para instalar todas as dependencias

    ```shell
    npm install --save-dev nodemon
    ```

  - Abra o o arquivo package.json, e insira o script "start" para iniciar a aplicação:

    ```json
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1",
      "start": "nodemon app.js"
    }
    ```

    Adicione o arquivo app.js no root do projeto 

  - Finalizando, inicie o projeto.

    ```shell
    npm run start
    ```
    Você deverá ter uma resposta com algo similar a isso:
    ```bash
    [nodemon] 3.1.10
    [nodemon] to restart at any time, enter `rs`
    [nodemon] watching path(s): *.*
    [nodemon] watching extensions: js,mjs,cjs,json
    [nodemon] starting `node app.js`
    [nodemon] clean exit - waiting for changes before restart
    ```


  ## 3. Editando e criando arquivos 
  
  Nesta etapa, criaremos e escreveremos alguns arquivos específicos para o projeto.

  ### 3.1 app.js 

  - Crie o arquivo **app.js** na pasta root do projeto e inclua as seguintes linhas:

    ```js
    require('dotenv').config()
    const express = require('express')
    const mongoose = require('mongoose')
    const bcrypt = require('bcrypt')
    const jwt = require('jsonwebtoken')

    const app = express()

    app.get('/', (req, res)=>{
        res.status(200).json({msg: 'Bem vindo a nossa API!'})
    })

    app.listen(3000)
    ```

  ### 3.2 .gitignore

  - Crie o arquivo **.gitignore** na pasta root do projeto e inclua as seguintes linhas:
  
  ```js
  node_modules
  .env
  ```

  ## 4. Acessando a API 
 - Utilizando a Plataforma de API instalada e usando a rota GET, acesse a url http://localhost:3000/ para verificar se responde com a mensagem _Bem vindo a nossa API!_
 
    ```json
    {
      msg: 'Bem vindo a nossa API!'
    }
    ```