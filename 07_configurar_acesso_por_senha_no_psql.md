## Configurando o Acesso ao PostgreSQL: Usuários e Senhas

### Introdução
Este guia detalha como configurar o acesso ao banco de dados PostgreSQL.
Definição de senhas e ajuste das configurações de autenticação.

### Logando no PostgreSQL

**1. Logando como usuário `postgres`:**
```bash
  sudo -i -u postgres
```

Este comando permite que você faça login no sistema como o usuário postgres, que possui privilégios administrativos no banco de dados.

**2. Logando como o usuário atual:**
```bash
  psql
```
Se você criou um usuário no PostgreSQL com o mesmo nome do seu usuário no sistema, você pode conectar-se diretamente ao banco de dados usando este comando.

**Verificando a conexão::**
```bash
  \conninfo
```
Este comando exibe informações detalhadas sobre a sua conexão, incluindo o banco de dados, usuário e método de autenticação. A informação "via socket" indica que você está conectado localmente usando um socket Unix, o que é mais eficiente e seguro.

**Criando uma Senha para o Usuário:**
Por padrão, o usuário postgres não possui senha. Para adicionar uma senha:
```bash
    \password
```

**Configurando a Autenticação:**

Entendendo o pg_hba.conf:

O arquivo pg_hba.conf controla os métodos de autenticação usados para conectar ao servidor PostgreSQL. A linha:
```text
    local   all             postgres                                peer
```
indica que o usuário postgres pode se conectar localmente sem senha usando o método de autenticação `peer`.

**Alterando para autenticação por senha:**

**1. Localizar o arquivo:**
```bash
    show hba_file;
```

**2. Editar o arquivo:**
Abra o arquivo pg_hba.conf em um editor de texto com privilégios de root e altere a linha para:
```text
    local   all             postgres                                md5
```
Isso exigirá que você digite a senha ao se conectar como `postgres`.

**3. Reiniciar o serviço:**
```bash
    sudo systemctl restart postgresql
```