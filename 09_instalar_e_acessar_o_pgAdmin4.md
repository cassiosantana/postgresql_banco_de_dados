### Instalação em distribuições linux baseadas em debian: https://www.pgadmin.org/download/pgadmin-4-apt/

### Configuração do repositório

**Instale a chave pública para o repositório (se não tiver sido feito anteriormente):**
```bash
  curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```

**Crie o arquivo de configuração do repositório:**
- Nota: A variável `$(lsb_release -cs)` do comando abaixo pega o nome da release da distribuição linux. Se não for o Ubuntu poderá causar um problema e o processo não irá funcionar. No caso do mint 21.3 essa variavel retorna `virginia` e não uma release válida do Ubuntu. Nesse caso, você deve definir manualmente o nome da distribuição (por exemplo, jammy).
```bash
  sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```

### Instale o pgAdmin

**Instale para ambos os modos, desktop e web:**
```bash
  sudo apt install pgadmin4
```

**Instale apenas para o modo desktop:**
```bash
  sudo apt install pgadmin4-desktop
```

**Instale apenas para o modo web:**
```bash
  sudo apt install pgadmin4-web
```

**Configure o servidor web, se você instalou o pgadmin4-web:**
```bash
  sudo /usr/pgadmin4/bin/setup-web.sh
```

### Definindo uma conexão com o servidor do postgresql:

1. Add New Server
   - Na guia `General` Definir o nome da conexão(sugiro o nome do local do servidor)
   - Na aba `Connection` definir o endereço padrão quando o servidor é o da nossa máquina: `127.0.0.1`.
   - Porta `5432`
   - Database `postgres`
   - Username `postgres`
   - Password `senha_do_servidor`
