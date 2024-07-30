## Criando e Excluindo Usuários no PostgreSQL

### O que são `createuser` e `dropuser`?
`createuser` e `dropuser` são comandos auxiliares (**wrappers**) que simplificam a criação e exclusão de usuários no PostgreSQL. Eles encapsulam comandos SQL mais complexos, facilitando o gerenciamento de usuários.

### Criando um Novo Usuário
**Pré-requisitos:**
* Estar logado como um superusuário do PostgreSQL: `sudo -i -u postgres`

**Comando básico:**
```bash
  createuser -dPs <nome_do_usuario>
```
- -d: Cria um banco de dados com o mesmo nome do usuário.
- -P: Solicita uma senha para o novo usuário.
- -s: Torna o usuário um superusuário (com todos os privilégios).

Opções adicionais:

- --interactive: Permite configurar o usuário interativamente.

**Exemplo:**

```bash
  createuser -dPs cassio
```

**Listando Usuários**
Para listar os usuários e suas permissões, utilize:
```bash
  \du
```

Isso exibirá uma tabela com as seguintes informações (entre outras):

- Superuser
- Create role
- Create DB
- Replication
- Bypass RLS

**Configurando Permissões no pg_hba.conf**
O arquivo pg_hba.conf controla as conexões ao servidor PostgreSQL. Para permitir que o novo usuário se conecte, adicione uma linha semelhante à seguinte:
```text
    local   all             cassio                                  md5
```


**Resultado**
```text

Database administrative login by Unix domain socket
local   all             postgres                                md5
local   all             cassio                                  md5
```

**Reinicie o serviço PostgreSQL**
```bash
  sudo systemctl restart postgresql
```

**Conectando-se ao PostgreSQL**
```bash
    psql
```

- Importante: Se você não especificar um banco de dados, o PostgreSQL tentará conectar-se ao banco de dados com o mesmo nome do seu usuário do sistema.



**Especificando o banco de dados**
```Bash
  psql -U cassio -d meu_banco_development
```

- -U: Nome do usuário do banco de dados.
- -d: Nome do banco de dados.

**Verificando usuário e banco de dados**
```bash
    \conninfo
```

**Erros Comuns**
- Banco de dados inexistente: Se você receber a mensagem "database "cassio" does not exist", verifique se o banco de dados foi criado corretamente ou especifique o nome correto do banco de dados.

### Excluindo um Usuário
**Pré-requisitos:**
* Estar logado como um superusuário do PostgreSQL: `sudo -i -u postgres`

```bash
    dropuser <nome_do_usuario>
```

**Erros Comuns**
- Excluir usuário proprietário de banco de dados: não é permitido excluir esse tipo de usuário.
```text
    dropuser: error: removal of role "cassio" failed: ERROR:  role "cassio" cannot be dropped because some objects depend on it
```