https://youtu.be/Ft3F7wWA-x8?list=PLucm8g_ezqNoAkYKXN_zWupyH6hQCAwxY

Verificar a versão do psql

```bash
psql --version
```

Ao rodar o comando abaixo poderemos ver que o psql também pode executar comandos diretamente no terminal, além de dentro de usa interface.

```bash
psql --help
```

Para logar no psql é preciso que seja com o usuário específico que tenha autorização para isso no psql. Quando instalamos o postgresql automaticamente criamos o superusuário `postgres` que é administrador e pode fazer qualquer coisa dentro do psql.

```bash
sudo -i -u postgres
```
Com este comando acima o que fizemos foi mudar o usuário e note que ainda é possível ver o nome da máquina. Isso significa que ainda não estamos no psql. Ainda estamos no terminal do linux. Mas agora sim devemos digitar:

psql
```

O prompt padrão do psql é esse `postgres=#` e note que o `#` indica que estamos logados como super usuários e o `postgres` se refere ao banco de dados logado.

Alterar senha

```bash
\password
```

Para ver os comandos disponíveis

```bash
\h
```

Também podemos chamar o `\h` para um comando sql específico e receberemos informações deste determinado comando.

```bash
\h create role

Command:     CREATE ROLE
Description: define a new database role
Syntax:
CREATE ROLE name [ [ WITH ] option [ ... ] ]

where option can be:

      SUPERUSER | NOSUPERUSER
    | CREATEDB | NOCREATEDB
    | CREATEROLE | NOCREATEROLE
    | INHERIT | NOINHERIT
    | LOGIN | NOLOGIN
    | REPLICATION | NOREPLICATION
    | BYPASSRLS | NOBYPASSRLS
    | CONNECTION LIMIT connlimit
    | [ ENCRYPTED ] PASSWORD 'password' | PASSWORD NULL
    | VALID UNTIL 'timestamp'
    | IN ROLE role_name [, ...]
    | IN GROUP role_name [, ...]
    | ROLE role_name [, ...]
    | ADMIN role_name [, ...]
    | USER role_name [, ...]
    | SYSID uid

URL: https://www.postgresql.org/docs/14/sql-createrole.html
```

Também é possível verificar comandos administrativos

```bash
\?
```

Listar banco de dados

```bash
\l
```

Listar usuários

```bash
\du
```

Mudar o banco de dados acessado no momento

```bash
\c <BANCO_DESTINO>
```

Listar as tabelas do banco conectado

```bash
\d
```

Listar as tabelas administrativas do postgres

```bash
\dS
```

É possível alternar entre o psql e o terminal do linux quando desejamos executar algum comando sem necessáriamente sair do psql

```bash
\!
```

E ao terminar o que desejamos realizar no terminal podemos voltar para o psql basta executar o `exit`

Mas na verdade não precisamos nem alternar, pois podemos executar o comando do terminal linux pelo psql desta forma

```bash
\! pwd
```

Para sair do psql