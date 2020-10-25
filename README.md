<h1 align="center">Proffy Service</h1>
<p align="center">
<img alt="GitHub language count" src="https://img.shields.io/github/languages/count/hernanbs/snl-proffy-server?style=flat-square">
<img alt="GitHub top language" src="https://img.shields.io/github/languages/top/hernanbs/snl-proffy-server?style=flat-square">
<img alt="GitHub code size in bytes" src="https://img.shields.io/github/languages/code-size/hernanbs/snl-proffy-server?color=%232ec73a&style=flat-square">
<img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/hernanbs/snl-proffy-server?color=%232ec73a&style=flat-square">
<img alt="GitHub" src="https://img.shields.io/github/license/hernanbs/snl-proffy-server?style=flat-square">
</p>

### :computer: Introdução
  Aplicação REST que disponibiliza acesso e cadastro de informações sobre professores e suas aulas disponíveis, por meio de requisições HTTP em um formato padronizado JSON.
  
  Projeto feito inteiramente com TypeScript utilizando SQLite para armazenar dados utilizados pelo sistema, também foi utilizado a biblioteca Knex.js para simblificar a conexão com o SQLite.
  
### :rocket: Instalação
* Necessário instalar [SQLite]([https://www.sqlite.org/index.html](https://www.sqlite.org/index.html)).
* Execute também os seguintes comndos:
```bash
# Instalar dependências
	yarn install
# Executar projeto
	yarn start
```

### :closed_book: HTTP Endpoints

|    | Verbos HTTP | URI                                                                          |
|----|:-----------:|------------------------------------------------------------------------------|
| 01 | GET       | http://localhost:3333/classes    |
| 02 | POST      | http://localhost:3333/classes    |
| 03 | GET       | http://localhost:3333/connections|
| 04 | POST      | http://localhost:3333/connections|

#### :pushpin:  Descrição 

#### 01 - Listar todas as aulas
 * Não necessita de body na requisição
 * Retorno no formato: 
  ```json
  [
    {
      "id": "conteudo",
      "subject": "conteudo" ,
      "cost": 99.99,
      "name": "conteudo",
      "avatar": "conteudo",
      "bio": "conteudo",
      "whatsapp": "conteudo",
      "schedule": "{}"
    }
  ]
  ```
#### 02 - Adiciona uma aula a base de dados
* body da requisição necessário.
  ```json
  {
      "subject": "conteudo" ,
	    "cost": 99.99,
	    "name": "conteudo",
	    "avatar": "conteudo",
	    "bio": "conteudo",
	    "whatsapp": "conteudo",
	    "schedule": "{}"
  }
  ```  
 * Retorno no formato *inteiro*, numero de id
#### 03 - Quantidade de conexões
 * Não necessita de body na requisição
 * Retorno no formato: 
  ```json
  [
    {
	    "total": 999,
    }
  ]
  ```
#### 04 - Adiciona uma conexão a base de dados
* body da requisição necessário.
  ```json
  {
      "user_id": "conteudo" ,
  }
  ```
 * Retorno no formato *inteiro*, numero de id
### :hammer_and_wrench: STATUS DAS RESPOSTAS
* 200: OK
* 201: Criado
* 204: Resposta sem conteúdo
* 3xx: Redirection
* 400: Má requisição
* 404: Página não encontrada
* 500: Erro interno do servidor
