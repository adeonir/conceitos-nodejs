<h1 align="center">
  <img src=".assets/logo-gostack.svg" atl="GoStack Bootcamp" />
</h1>

<h3 align="center">
  Desafio 2: Conceitos do Node.js
</h3>

<p align="center">
  Desafio desenvolvido durante o <a href="https://rocketseat.com.br/gostack">Bootcamp GoStack</a> da Rocketseat.
  <br />
  <br />
  <a href="#tecnologias">Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#sobre-o-desafio">Sobre o desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#instalação-e-execução">Instalação e execução</a>
</p>

## Tecnologias

- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- [Insomnia](https://insomnia.rest/)

## Sobre o desafio

Nesse desafio, eu criei uma aplicação para teinar o que eu aprendi até agora no Node.js!

Essa será uma aplicação para armazenar repositórios em meu portfolio, que irá permitir criação, listagem, atualização e remoção dos repositórios. Além disso irá permitir que os repositórios possam receber "likes".

### Rotas da aplicação
- **`POST /repositories`**: A rota deve receber `title`, `url` e `techs` dentro do corpo da requisição, sendo a URL o link para o github desse repositório. Ao cadastrar um novo projeto, ele deve ser armazenado dentro de um objeto no seguinte formato: `{ id: 'uuid', title: 'Desafio Node.js', url: 'https://github.com/...', techs: ['Node.js', 'React', ...], likes: 0 }`. Certifique-se de que ID seja um UUID, e de sempre iniciar os likes em 0;
- **`GET /repositories/`**: Rota que vai listar todos os repositórios;
- **`PUT /repositories/:id`**: A rota deve alterar apenas o `title`, a `url` e as `techs` do repositório que possua o `id` igual ao `id` presente nos parâmetros da rota;
- **`DELETE /repositories/:id`**: A rota deve deletar o repositório com o `id` presente nos parâmetros da rota;
- **`POST /repositories/:id/like`**: A rota deve aumentar o número de likes do repositório específico escolhido através do `id`presente nos parâmetros da rota, a cada chamada dessa rota, o número de likes deve ser aumentado em 1.

### Específicação dos testes

Para esse desafio temos os seguintes testes:

- **`should be able to create a new repository`**: Para que esse teste passe, a aplicação deve permitir que um repositório seja criado, e retorne um json com o projeto criado.

- **`should be able to list the repositories`**: Para que esse teste passe, a aplicação deve permitir que seja retornado um array com todos os repositórios que foram criados até o momento.

- **`should be able to update repository`**: Para que esse teste passe, a aplicação deve permitir que sejam alterados apenas os campos `url`, `title` e `techs`.

- **`should not be able to update a repository that does not exist`**: Para que esse teste passe, deve validar na rota de update se o id do repositório enviado pela url existe ou não. Caso não exista, retornar um erro com status `400`.

- **`should not be able to update repository likes manually`**: Para que esse teste passe, não deve permitir que a rota de update altere diretamente os likes desse repositório, mantendo o mesmo número de likes que o repositório já possuia antes da atualização. Isso porque o único lugar que deve atualizar essa informação é a rota de responsável por aumentar o número de likes.

- **`should be able to delete the repository`**: Para que esse teste passe, deve permitir que a a rota de delete exclua um projeto, e ao fazer a exclusão, ele retorne uma resposta vazia, com status `204`.

- **`should not be able to delete a repository that does not exist`**: Para que esse teste passe, deve validar na rota de delete se o id do repositório enviado pela url existe ou não. Caso não exista, retornar um erro com status `400`.

- **`should be able to give a like to the repository`**: Para que esse teste passe, a aplicação deve permitir que um repositório com o id informado possa receber likes. O valor de likes deve ser incrementado em 1 a cada requisição, e como resultado, retornar um json contendo o repositório com o número de likes atualizado.

- **`should not be able to like a repository that does not exist`**: Para que esse teste passe, deve validar na rota de like se o id do repositório enviado pela url existe ou não. Caso não exista, retornar um erro com status `400`.

## Instalação e execução

```bash
# Clone esse repositório
$ git clone https://github.com/adeonir/gostack-conceitos-nodejs conceitos-nodejs

# Entre no diretório
$ cd conceitos-nodejs

# Instale as dependências
$ yarn

# Rode a aplicação
$ yarn dev

# Rode os testes
$ yarn test
```

## Licença

Esse projeto está sob a licença MIT.

---

Made with ♥️ by Adeonir Kohl