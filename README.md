# Autenticação com Node.js e MongoDB com JWT - Login e Registro com Node.js
  
  # Instalações importantes 

  Antes de prosseguir, é necessário ter algumas instalações na sua maquina. Caso já tenha instalados, pule para a próxima etapa.

  ## Node.js/NPM
  - Baixe o Node.js em https://nodejs.org/en/download e, após a instalação, execute o seguinte commando em algum terminal para verificar se a instalação foi bem sucedida.
    ### Verificar a versão do Node.js
    ```shell
    node -v
    ```
    ### Verificar a versão do NPM
    ```shell
    npm -v
    ```
  
  ## MongoDB
  - Crie uma conta https://account.mongodb.com/account/login ou acesse usando a conta do Google.
  
  ## Plataforma de API
  - Baixe/Instale o Postman em https://www.postman.com/, ou;
  - Baixe/Instale o Insomnia em https://insomnia.rest/download/.


# Criando o Projeto
  Foi utilizado o VSCode como IDE para desenvolvimento. 

  ## Configurando o Projeto 
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
    ...
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1",
      "start": "nodemon app.js"
    }
    ...
    ```

    Adicione o arquivo app.js no root do projeto 

  - Finalizando, inicie o projeto.

    ```shell
    npm run start
    ```
