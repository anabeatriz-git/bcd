# Resumo dos Seminários de SQL

Os seminários tem como objetivo promover a troca de conhecimentos e experiências, permitindo discussões aprofundadas sobre temas relevantes e estimulando a análise crítica e a inovação.

## Importância das transações SGBD

A transação do banco de dados é um sistema onde atomicidade, consistência, isolamento e
durabilidade tem que andar juntas para que a estrutura permaneça correta e confiável, independentemente de o que aconteça.

### Atomicidade:
 Tudo ou nada. Se alguma parte da transação falhar, nada é feito. É como se você não tivesse pedido nada.

### Consistência: 
A transação deve levar o banco de dados de um estado válido a outro estado válido. Ou seja, não pode deixar os dados em um estado confuso ou incorreto.

### Isolamento:
 As transações devem acontecer como se fossem as únicas ocorrendo. Assim, uma transação não interfere em outra que esteja acontecendo ao mesmo tempo, evitando conflitos.

### Durabilidade: 
Uma vez que uma transação é completada, suas mudanças são permanentes, mesmo que ocorra um problema depois (como uma queda de energia).

Se todas as operações forem executadas com sucesso e sem erros. A transação pode
ser finalizada com um comando COMMIT.

## Funções de agregação

As funções de agregação em bancos de dados ajudam a resumir e analisar dados de forma eficiente. Aqui estão algumas delas explicadas de maneira simples:

### COUNT(*):
 Imagine que você tem uma lista de alunos. O COUNT conta quantos alunos estão na lista. É útil para saber o total de registros.

### SUM(coluna):
 Se você tem uma coluna com as notas de todos os alunos, a função SUM soma todas as notas. Assim, você pode saber a soma total das notas.

### AVG(coluna):
 Usando o mesmo exemplo, o AVG calcula a média das notas. Isso ajuda a entender como os alunos se saíram em geral.

### MIN(coluna): 
Essa função encontra a menor nota entre os alunos. É útil para ver quem teve o pior desempenho.

### MAX(coluna): 
Ao contrário do MIN, o MAX encontra a maior nota. Isso ajuda a identificar o aluno com a melhor performance.

### GROUP BY:
Essencial, pois agrupa valores iguais.

## Indexação e Performance

Um índice é uma estrutura adicional que aumenta a rapidez na recuperação de registros em uma tabela, tornando a busca mais eficiente.

Em sistemas com grandes volumes de dados, a indexação pode diminuir consideravelmente o tempo de resposta das consultas.

### Quando utilizar?

Filtros Comuns: Se você frequentemente consulta uma tabela utilizando filtros em colunas específicas, essas colunas devem ser indexadas.

Consultas de Junção: Colunas utilizadas em JOIN devem ser indexadas para evitar que o banco de dados realize varreduras completas nas tabelas envolvidas.

Ordenação e Agregações: Índices podem otimizar o desempenho de operações que envolvem ordenações ou cálculos agregados.

## Joins em SQL

Joins são operações que combinam dados de duas ou mais tabelas com base em uma condição comum, geralmente usando chaves primárias e chaves estrangeiras. Eles permitem acessar dados relacionados em diferentes tabelas.

Tipos de Joins:
### INNER JOIN:

Como Funciona: Usa uma condição para combinar registros de diferentes tabelas. Retorna apenas as linhas que satisfazem essa condição.
Resultado: Somente as correspondências são incluídas; linhas sem correspondência são ignoradas.
### LEFT JOIN (ou LEFT OUTER JOIN):

Descrição: Retorna todos os registros da tabela à esquerda e as correspondências da tabela à direita. Se não houver correspondência, os resultados da tabela à direita serão NULL.
Exemplo: Se tiver tabelas de Clientes e Pedidos, retornará todos os clientes, mesmo os que não têm pedidos.
### RIGHT JOIN (ou RIGHT OUTER JOIN):

Descrição: Retorna todos os registros da tabela à direita e as correspondências da tabela à esquerda. Se não houver correspondência, os resultados da tabela à esquerda serão NULL.
Exemplo: Retornará todos os pedidos, mesmo aqueles sem clientes correspondentes.
### FULL OUTER JOIN:

Descrição: Combina os resultados de um LEFT JOIN e um RIGHT JOIN, retornando todos os registros de ambas as tabelas. Quando não há correspondência, os resultados aparecem como NULL.
Exemplo: Retornará todos os clientes e todos os pedidos, independentemente de haver correspondências.

## OPERADORES LÓGICOS

O que é?
Os operadores são ferramentas utilizadas para manipulação e consulta de dados, permitindo a execução de operações complexas, como busca, filtragem e definição de condições.

### AND

Uso: Combina duas ou mais condições, retornando verdadeiro apenas se todas forem verdadeiras.
Exemplo em SQL:

### OR

Uso: O operador OR é empregado para juntar duas ou mais condições em uma consulta, onde pelo menos uma delas deve ser verdadeira para que o registro seja incluído no resultado. Veja o exemplo:

### NOT

Uso: Inverte o valor de verdade de uma condição. Retorna verdadeiro se a condição for falsa.

### IN

O operador IN é usado para verificar se um valor está presente em uma lista de valores definidos. É uma forma compacta de realizar várias comparações.

### NOT IN

O operador NOT IN faz o contrário do IN, verificando se um valor não está presente na lista de valores especificados.

### BETWEEN

O operador BETWEEN é utilizado para filtrar resultados dentro de um intervalo específico, aplicável a números, datas ou outros tipos de dados. O intervalo inclui os limites.

### LIKE

O operador LIKE é empregado em uma cláusula WHERE para buscar padrões dentro de uma coluna de texto. É especialmente útil quando o valor exato não é conhecido, permitindo buscas com base em padrões ou partes de palavras.

### IS NULL

O operador IS NULL é utilizado para verificar se um valor em uma coluna é nulo, ou seja, se não foi inserido ou é desconhecido.

Subconsultas SQL
O que são?
Subconsultas são consultas SQL inseridas dentro de outra consulta, permitindo a recuperação de dados de forma mais específica, filtrada ou agregada.

## Aplicações:

- Filtrar resultados com critérios complexos.
- Realizar cálculos e agregações sem precisar criar tabelas intermediárias.
### Quando Usar
Filtragem de Dados: Para filtrar resultados com base em um conjunto de dados que não pode ser obtido em uma única consulta.

Cálculos Agregados: Para realizar cálculos que dependem de dados agregados em outras tabelas.
Verificações de Existência: Para checar se um registro existe em outra tabela.
Atualizações Condicionais: Para atualizar registros com base em condições que envolvem dados de outras tabelas.

### Vantagens e Desvantagens

Vantagens:

- Maior clareza em consultas complexas.
- Elimina a necessidade de tabelas temporárias.
- Flexibilidade na manipulação de dados.

Desvantagens:

- Subconsultas correlacionadas podem ser mais lentas, pois são avaliadas para cada linha da consulta externa.
- Em consultas muito grandes, podem impactar o desempenho.

## SUM, AVG, COUNT e MIN/MAX: Funções Agregadas
As funções agregadas são ferramentas essenciais para resumir e analisar dados, proporcionando insights valiosos ao condensar informações e realizar cálculos.

1. Simplificação de Dados
As funções agregadas facilitam a análise de grandes conjuntos de dados, tornando o processo mais rápido.

2. Insights Relevantes
Permitem extrair totais, médias, contagens e valores extremos, oferecendo uma visão abrangente.

3. Tomada de Decisões
Fornecem uma perspectiva geral dos dados, auxiliando decisões estratégicas.

### Funções Agregadas Principais

SUM: Calcula a soma de valores numéricos.

Aplicações: Total de vendas, lucros, quantidades.
AVG: Calcula a média aritmética.

Aplicações: Média de vendas por mês, idade média de clientes.
COUNT: Conta o número de registros.

Contagem Simples: COUNT(*) conta todos os registros.

Contagem Condicional: COUNT(coluna) conta registros não nulos.

### Diferenças entre Funções

SUM: Soma de valores.

AVG: Média de valores.

COUNT: Número de registros.

Exemplos de Aplicações
Análise de Vendas: Total de vendas por região e média de valor de pedido.
Comportamento do Cliente: Contagem de clientes por faixa etária e média de compras.
Análise Financeira: Lucro total e número de transações.
MIN e MAX
As funções MIN e MAX identificam valores extremos em conjuntos de dados:

MIN: Retorna o menor valor (ex: menor preço).
MAX: Retorna o maior valor (ex: maior venda).
Aplicações de MIN e MAX
Preço Mínimo: Menor preço de um produto.
Temperatura Máxima: Temperatura mais alta registrada.
Estoque Mínimo: Menor nível de estoque de um produto.


