## [Tópico T03b] - Requisitos de Dados - BD Locadora de Veículos
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

### Introdução

Uma **locadora de veículos** utiliza um **software**, que apoia a gestão e a operação do negócio.

O software para a locadora de veículos atua na gestão e na operação do empréstimo de veículos para clientes:
- Veículos são locados a partir do contato entre clientes e atendentes da locadora.
- Qualquer atendente é um ser humano ou um _software bot_.
- **Atendentes** fazem buscas no banco de dados, para apoiar os clientes em suas decisões.
- O **administrador da locadora** toma decisões táticas, visando a conhecer os perfis de locação e clientes, para atuar na gestão operacional e campanhas de divulgação.
- O **gerente financeiro** da locadora lida essencialmente com aspectos monetários do negócio. 
- Os **mecânicos** atuam conforme uma agenda diária de trabalho, que visa a reduzir o tempo dos veículos em estado de manutenção.

### Locação de veículos

As locações são realizadas de acordo com a demanda própria de cada cliente.<br>
Em cada locação, o cliente usualmente pode fazer cinco escolhas:<br>
&#9745; <ins>**Escolha-01:**</ins> O modelo de veículo de uma determinada marca.<br>
&#9745; <ins>**Escolha-02:**</ins> Os acessórios para o veículo:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;por exemplo, cadeira de criança, cobertor, etc.<br>
&#9745; <ins>**Escolha-03:**</ins> Se a locação inclui o seguro do veículo.<br>
&#9745; <ins>**Escolha-04:**</ins> O plano de locação, a saber:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;plano sem benefícios,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;plano com benefício para a quantidade n dias,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;plano com benefício para o dia n da semana.<br>
&#9745; <ins>**Escolha-05:**</ins> O período de locação: data inicial e data final.

Sobre as escolhas do cliente, vale ressaltar:<br>
&#9745; <ins>**Escolha-01:**</ins> Cada modelo de veículo possui um valor de locação diária:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;O valor da locação diária do veículo é determinado pelo modelo do veículo.<br>
&#9745; <ins>**Escolha-02:**</ins> Cada acessório ocasiona um acréscimo percentual ao valor da locação diária:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;por exemplo, a ‘cadeirinha de bebê’ é um acessório que acrescenta 2% (dois por cento) ao valor da locação diária;<br>
&#9745; <ins>**Escolha-03:**</ins> Se a locação inclui o seguro do veículo, há um acréscimo percentual ao valor da locação diária, conforme o modelo de veículo:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;por exemplo, o seguro para o modelo ‘fusca’ acrescenta 4% (quatro por cento) ao valor da locação diária, mas o modelo ‘corolla’ acrescenta 5% (cinco por cento).<br>
&#9745; <ins>**Escolha-04:**</ins> Em cada plano com benefícios, há um decréscimo percentual ao valor da locação diária:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;(a) o **plano com benefício para a quantidade _n_ dias** resulta em um decréscimo percentual, se o número de dias locados for igual ou superior a **n** dias;<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;(b) o **plano com benefício para o dia _n_ da semana** resulta em um decréscimo percentual, se o dia **n** da semana estiver no período de locação, tal que **n** pode ser 1, 2, …, 7 (para domingo, segunda, …, sábado, respectivamente).<br>
&#9745; <ins>**Escolha-05:**</ins> As datas inicial e final de um período de locação não podem ser idênticas.

O cálculo do valor final de uma locação deve considerar:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;O período de locação;<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;O valor de locação diária; e<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&#9728;Os percentuais de decréscimo e acréscimo aplicados.<br>
Por exemplo, considere a locação: o período é 07 dias; o valor da locação é 30 reais de acordo com o modelo de veículo; o acessório A tem acréscimo de 05%; o acessório B tem acréscimo de 07%; o seguro do veículo tem acréscimo de 10% de acordo com o modelo de veículo; e o plano com benefício tem decréscimo de 20%. O valor final da locação é 7*30*1,02 = 214,20 reais.

### Breve glossário

- **Marca de veículo:** montadora responsável para fabricar o veículo; exemplos: Toyota e Honda.
- **Modelo de veículo:** tipo de veículo disponível para locação; exemplos: Corolla e Civic.
- **Período de locação:** sequência de dias limitado, definido pelo intervalo fechado entre duas datas.
- **Comissão de locação:** valor pago ao atendente que iniciou as locações, correspondente a 2,5% do valor faturado (valor final) em cada locação.

### Perfis de usuários

- **Atendente:** realiza a venda da locação, a partir do contato com o cliente. Apresenta ao cliente: disponibilidade de veículos (veículos prontos para locação), valores de diárias, acessórios, etc.
- **Administrador:** busca informações sobre volume de locações (por cliente, modelo de veículo), produtividade de funcionários (mecânico, atendente).
- **Gerente Financeiro:** busca informações sobre faturamento de locações e vendas, e despesas da locadora.
- **Mecânico:** busca informações sobre agenda de manutenções, manutenções realizadas e pendentes, peças disponíveis.

### Demandas informacionais para <ins>Atendente/Cliente</ins>

1. Qual foi a duração (em dias) da última locação do cliente X?
2. Quais veículos estão disponíveis para locação por um número X de dias, limitado ao valor  X?
3. Quais são os veículos disponíveis para locação do modelo X?
4. Quais são os veículos disponíveis para locação que contêm sete lugares?
5. Qual o detalhamento financeiro da última locação do cliente X?
6. Quais os modelos de veículo que possuem o acessório X?

### Demandas informacionais para <ins>Administrador</ins>

1. Quantas manutenções foram realizadas por cada mecânico no período X ?
2. Qual é o modelo com maior número de dias locados no período X ?
3. Quais os clientes que mais alugaram veículos no período X ?
4. Qual o modelo de veículo com mais ocorrências de manutenção corretiva no período X ?
5. Qual foi o atendente que mais alugou veículos no período X ?

### Demandas informacionais para <ins>Gerente Financeiro</ins>

1. Qual é o valor total faturado no período X ?
2. Qual é o custo total das manutenções executadas no período X ?
3. Qual a comissão para cada atendente, correspondente às locações no período X ?
4. Qual foi o faturamento relativo ao modelo X no período Y ?
5. Quais o valor total cobrado por tipo de acessório no período X?
6. Qual foi o resultado do veículo X desde a sua aquisição? Considerar valor de compra, receitas com locação, despesas com manutenção e venda (se for o caso).

### Demandas informacionais para <ins>Mecânico</ins>

1. Quais os veículos programados ao mecânico X, para manutenção corretiva e preventiva em uma data ?
2. Qual o histórico de manutenção do veículo X ?
3. Quais os veículos que estão com término de manutenção em atraso ?
4. Quais os motivos de manutenção corretiva programadas para uma data ?
5. Qual o custo associado a serviços executados e a peças usadas em uma manutenção específica?

## Não há atividade para este tópico, excepcionalmente.
