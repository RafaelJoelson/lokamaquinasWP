Aqui está um exemplo de como você pode estruturar o `README.md` para o projeto **lokamaquinas.com.br**. Esse documento inclui instruções para configurar o ambiente com Docker, como rodar o WordPress e outras informações relevantes:

---

# Lokamaquinas.com.br

Este projeto é o desenvolvimento do site de locação de máquinas **Lokamaquinas** utilizando o WordPress, com a infraestrutura do ambiente de desenvolvimento gerenciada via Docker.

## Descrição do Projeto

O site **lokamaquinas.com.br** é voltado para a locação de máquinas, facilitando o contato com os clientes diretamente através do WhatsApp. Este repositório contém o código do site utilizando WordPress, configurado para facilitar o desenvolvimento e deploy.

## Tecnologias Utilizadas

- **WordPress**: CMS utilizado para gerenciar o conteúdo do site.
- **Docker**: Ferramenta de containerização utilizada para configurar o ambiente de desenvolvimento.
- **MySQL**: Banco de dados relacional usado para armazenar dados do WordPress.
  
## Pré-requisitos

Para rodar este projeto localmente, você precisa ter o Docker e Docker Compose instalados em sua máquina. Certifique-se de que as versões instaladas sejam compatíveis:

- Docker: versão >= 20.10
- Docker Compose: versão >= 1.29.2

## Instruções para Rodar o Projeto Localmente

### 1. Clone o Repositório

```bash
git clone https://github.com/seu-usuario/lokamaquinas.com.br.git
cd lokamaquinas.com.br
```

### 2. Configuração do Ambiente

O ambiente está configurado utilizando Docker e Docker Compose. Certifique-se de que os volumes locais foram criados para armazenar os dados do WordPress e do banco de dados.

### 3. Subindo o Ambiente com Docker Compose

Para rodar o ambiente, execute o seguinte comando:

```bash
docker-compose up -d
```

Isso irá:

- Inicializar um contêiner com WordPress na porta 8000.
- Inicializar um contêiner MySQL para o banco de dados.

### 4. Acesso ao WordPress

Após inicializar o ambiente, você pode acessar o WordPress no navegador através do seguinte endereço:

```
http://localhost:8000
```

### 5. Configurações do Banco de Dados

As credenciais do banco de dados MySQL estão definidas no arquivo `docker-compose.yml`:

- **Usuário**: root
- **Senha**: example
- **Nome do banco de dados**: wordpress

Essas informações serão utilizadas durante a instalação inicial do WordPress.

## Configurações Adicionais

### PHP Settings

Se precisar aumentar o limite de upload ou ajustar outras configurações PHP, utilize as variáveis de ambiente configuradas no `docker-compose.yml`:

```yaml
- PHP_UPLOAD_MAX_FILESIZE=512M
- PHP_POST_MAX_SIZE=512M
```

### Volumes Persistentes

Os seguintes volumes são utilizados para persistir os dados da aplicação:

- `wp-data`: Para armazenar os arquivos do WordPress.
- `db-data`: Para persistir os dados do MySQL.

### Logs e Debugging

Caso precise verificar logs de erros ou problemas de execução, utilize os comandos abaixo:

- Ver logs do WordPress:
  ```bash
  docker-compose logs wordpress
  ```
- Ver logs do MySQL:
  ```bash
  docker-compose logs db
  ```

### 6. Parando o Ambiente

Para parar os contêineres rodando, utilize:

```bash
docker-compose down
```

## Deploy

Para fazer o deploy do WordPress para o ambiente de produção, os arquivos persistidos no volume `wp-content` podem ser enviados via FTP ou outro método para o servidor de hospedagem. Certifique-se de ajustar o arquivo `.htaccess` e as configurações de banco de dados para o ambiente de produção.

---

## Licença

Esse projeto é privado e sua distribuição não é permitida sem autorização.
Desevolvido por Rafael Joelson - Bratti Marketing Digital
rafaeljoelsonifsudeste@gmail.com

---

Esse `README.md` cobre todos os aspectos essenciais para a configuração e desenvolvimento do projeto **lokamaquinas.com.br** em um ambiente Docker, e também fornece instruções claras para rodar o ambiente localmente.