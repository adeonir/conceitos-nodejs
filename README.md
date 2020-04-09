<h3 align="center">
  Desafio: Conceitos do Node.js
</h3>

## Sobre o desafio

Nesse desafio, eu criei uma aplicação para teinar o que eu aprendi até agora no Node.js!

Essa será uma aplicação para armazenar repositórios em meu portfolio, que irá permitir criação, listagem, atualização e remoção dos repositórios. Além disso irá permitir que os repositórios possam receber "likes".

### Rotas da aplicação
- **`POST /repositories`**: A rota deve receber `title`, `url` e `techs` dentro do corpo da requisição, sendo a URL o link para o github desse repositório. Ao cadastrar um novo projeto, ele deve ser armazenado dentro de um objeto no seguinte formato: `{ id: 'uuid', title: 'Desafio Node.js', url: 'https://github.com/...', techs: ['Node.js', 'React', ...], likes: 0 }`. Certifique-se de que ID seja um UUID, e de sempre iniciar os likes em 0;
- **`GET /repositories/`**: Rota que vai listar todos os repositórios;
- **`PUT /repositories/:id`**: A rota deve alterar apenas o `title`, a `url` e as `techs` do repositório que possua o `id` igual ao `id` presente nos parâmetros da rota;
- **`DELETE /repositories/:id`**: A rota deve deletar o repositório com o `id` presente nos parâmetros da rota;
- **`POST /repositories/:id/like`**: A rota deve aumentar o número de likes do repositório específico escolhido através do `id`presente nos parâmetros da rota, a cada chamada dessa rota, o número de likes deve ser aumentado em 1.
