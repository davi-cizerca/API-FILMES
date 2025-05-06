# API de Filmes com Flask, PostgreSQL e OMDb

Este projeto é uma API RESTful para consulta e cache de informações de filmes, utilizando Flask, PostgreSQL e integração com a API OMDb.

## Funcionalidades

- Consulta de filmes no banco de dados local.
- Caso o filme não esteja no banco local, busca automática na OMDb.
- Armazenamento em cache dos filmes consultados para futuras buscas.
- Remoção de filmes do cache.
- Limpeza total do cache.

## Como usar

### 1. Configuração do Banco de Dados

Crie um banco de dados PostgreSQL e um usuário com permissões adequadas.
**Importante:** Não coloque informações sensíveis (usuário, senha, host) diretamente no código ou na documentação.
Utilize variáveis de ambiente ou arquivos de configuração ignorados pelo Git.

Exemplo de string de conexão (NÃO USE NO CÓDIGO):
```
postgresql://usuario:senha@host:porta/nome_do_banco
```

### 2. Instalação

Clone o repositório e instale as dependências:
```bash
git clone <url-do-repositorio>
cd api-de-DWIII
pip install -r requirements.txt
```

### 3. Configuração da API OMDb

Obtenha uma chave gratuita em: https://www.omdbapi.com/apikey.aspx
No código, substitua o valor da variável `API_KEY` pela sua chave OMDb.

### 4. Executando a API

```bash
python App/database.py
```

A API estará disponível em `http://localhost:5000`.

### 5. Exemplos de uso

Veja o arquivo `App/req.http` para exemplos de requisições HTTP.

## Rotas

- `GET /filmes`  
  Lista todos os filmes do banco local.

- `GET /filmes/<titulo>`  
  Busca um filme pelo título (primeiro no banco local, depois na OMDb).

- `DELETE /filmes/<id>`  
  Remove um filme do banco local pelo ID.

- `POST /filmes/limpar`  
  Limpa todo o cache de filmes.

## Segurança

- **Nunca exponha informações sensíveis** (usuário, senha, host do banco, chave OMDb) em arquivos públicos ou no repositório.
- Use variáveis de ambiente ou arquivos `.env` (adicionados ao `.gitignore`) para armazenar dados sensíveis.

## Licença

Este projeto é apenas para fins educacionais.

---

