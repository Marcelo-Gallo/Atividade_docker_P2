# CRUD de Contatos em PHP com Docker

Projeto de exemplo de um CRUD clássico em PHP, utilizando MySQL e Docker.

## Funcionalidades

- Cadastro de contatos
- Listagem, edição e exclusão de contatos
- Interface responsiva com Bootstrap

## Como executar

1. **Clone o repositório**
2. **Suba os containers com Docker Compose:**
   ```sh
   docker-compose up --build
   ```
3. **Acesse a aplicação:**
   - [http://localhost:80](http://localhost:80) — Aplicação PHP (`gallo-php`)
   - [http://localhost:8080](http://localhost:8080) — Adminer (`gallo-adminer`), gerenciador do banco

> **Observação:**  
> Todos os serviços Docker deste projeto rodam em `localhost` nas portas especificadas acima.  
> Como os containers estão conectados à rede Docker chamada `ativ_docker`, eles podem se comunicar entre si utilizando o nome do serviço definido no [`docker-compose.yml`](docker-compose.yml) (por exemplo, `mysql` para o banco de dados).  
> Isso é especialmente importante na configuração do PHP, onde o host do banco de dados deve ser `mysql` (e não `localhost`), conforme definido em [`web/config.ini`](web/config.ini).

## Estrutura

- `web/` — Código-fonte PHP
- `init.sql` — Script de criação da tabela no MySQL
- `docker-compose.yml` — Orquestração dos serviços
- `Dockerfile` — Imagem customizada do PHP

## Serviços Docker

- **gallo-php:** Container PHP/Apache, porta 80
- **gallo-mysql:** MySQL 8.0, porta 3306, dados persistidos em volume
- **gallo-adminer:** Adminer, porta 8080

## Credenciais padrão

- **Banco de dados:** `ativ_db`
- **Usuário:** `gallo`
- **Senha:** `gallo123`
- **Root:** `root_password`

---

## Sobre o projeto

Sinta-se à vontade para clonar este repositório e fazer modificações conforme desejar!

CRUD desenvolvido por Eder Pansani para uma atividade da disciplina de DW2. Atividade docker solicitada por Ubiratan Nascimento.
