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

### Limites do PostgreSQL:
Podem variar de acordo com a versão, de forma geral são estes.

- Tamanho do banco de dados é ilimitado
- Tamanho máximo de tabela é 32 TB
- Tamanho máximo de linha é 1,6 TB
- Tamanho máximo de campos é 1 GB
- Máximo de linhas por tabela é ilimitado
- Máximo de colunas por tabela é 250 - 1600 que será explicado melhor posteriormente no curso
- Máximo de índices por tablea é ilimitado 

### Terminologias:
Como o postgresql foi criado em ambiente universitário seus objetos são definidos em termos acadêmicos e baseados em álgebra relacional.
Indús

Termo Indústria -> Termo Postgres
Tabela          -> Relação
Linha		        -> Tupla 
Coluna		      -> Atributo                             
Bloco de datos  -> Página (quando o bloco está no disco)

### Quem utiliza:
Apenas algumas empresas que utilizam.

- Reddit
- Sony Online Games
- Skype
- Instagram
- Trip Advisor