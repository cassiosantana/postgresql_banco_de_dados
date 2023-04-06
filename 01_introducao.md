# Introdução ao PostgreSQL

<p>É um sistema de gerenciamento de banco de dados que começou como projeto **Ingres** na Universidade de Berkley por Michael Stonebraker.</p>
<p>Teve sua primeira versão lançada em 1997 e foi escrito em linguam C e é livre de código aberto e disponível em todas as plataformas.</p>

### Características:
- Compatível com ACID
- Banco transacional
- Suporta Particionamento
- Possui controle de concorrência multiversão
- Busca de texto completa
- Indexação com vários tipos de algoritmos.
- Permite operações de manutenção em modo online
- Operações geoespaciais (PostGIS)
- Possui linguagem procedural

### Conectividade:
- Via redes TCP/IP padrão. Possuit protocolo de transmissão de novo libpq, que também é o nome da biblioteca cliente que o implementa.
- Comunicação enviando comandos.
- Linguagem combina declarações em conformidade com o padrão sql:2008 e comandos de manutenção específicos.