# API de Filmes com Flask, PostgreSQL e OMDb

Este projeto é uma API RESTful para consulta e cache de informações de filmes, utilizando Flask, PostgreSQL e integração com a API OMDb.

## Funcionalidades

- Consulta de filmes no banco de dados local.
- Caso o filme não esteja no banco local, busca automática na OMDb.
- Armazenamento em cache dos filmes consultados para futuras buscas.
- Remoção de filmes do cache.
- Limpeza total do cache.

## Como usar

### 1. Instalação

Clone o repositório e instale as dependências:
```bash
git clone https://github.com/davi-cizerca/API-FILMES
cd API-FILMES
```

### 2. Configuração da API OMDb

Obtenha uma chave gratuita em: https://www.omdbapi.com/apikey.aspx
No código, substitua o valor da variável `API_KEY` pela sua chave OMDb.

### 3. Executando a API

```bash
python App/database.py
```

A API estará disponível em `http://localhost:5000`.

### 4. Exemplos de uso

Veja o arquivo `req.http` para exemplos de requisições HTTP.

## Rotas

- `GET /filmes`  
  Lista todos os filmes do banco local.

- `GET /filmes/<titulo>`  
  Busca um filme pelo título (primeiro no banco local, depois na OMDb).

- `DELETE /filmes/<id>`  
  Remove um filme do banco local pelo ID.

- `POST /filmes/limpar`  
  Limpa todo o cache de filmes.

---
