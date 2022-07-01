## [Tópico T11] - Álgebra Relacional - União, Interseção, Diferença
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

Para ilustrar as operações da Álgebra Relacional, considere os esquemas (conceitual e lógico) do BD Empresa.

<img src="../media/fig-der-empresa.jpg" width="400"><img src="../media/fig-esquema-logico-bdempresa.jpg" width="450">

### Operações UNIÃO (UNION), INTERSEÇÃO (INTERSECTION) e DIFERENÇA (MINUS)

UNIÃO, INTERSEÇÃO e DIFERENÇA são operações binárias baseadas na **Teoria dos Conjuntos**:
- Envolvem a comparação dos elementos (_tuplas_) presentes nos dois conjuntos (duas relações) de entrada.
- Para comparar as _tuplas_ presentes nas duas relações de entrada, as _tuplas_ devem ser do mesmo tipo, ou seja, deve haver **compatibilidade de união** (compatibilidade de tipo):
  - as relações **R (A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub>)** e **S (B<sub>1</sub>, B<sub>2</sub>, ..., B<sub>n</sub>)** são ditas ***união-compatíveis*** se:
    - tiverem o mesmo grau **n** (R e S têm o mesmo número de atributos); e
    - **dom(Ai) = dom( Bi)** para **1 ≤ i ≤ n** (cada par de atributos correspondente tem o mesmo domínio).
- UNIÃO: O resultado de **R ∪ S** é uma relação que inclui todas as _tuplas_ que estão em **R** ou em **S**, ou em **R** e **S**. _Tuplas_ duplicadas são eliminadas.
- INTERSEÇÃO: O resultado de **R ∩ S** é uma relação que inclui todas as _tuplas_ que estão em **R** e **S**.
- DIFERENÇA: O resultado de **R - S** é uma relação que inclui todas as tuplas que estão em **R**, mas não em **S**.

A figura abaixo ilustra a aplicação das operações.

<img src="../media/fig-algebra-uniao.jpg" width="400">

**Questões**:<br>
■ R ∪ S = S ∪ R ?<br>
■ R ∩ S = S ∩ R ?<br>
■ R - S = S - R ?<br>
■ R ∪ (S ∪ T ) = (R ∪ S) ∪ T ?<br>
■ (R ∩ S) ∩ T = R ∩ (S ∩ T) ?<br>

#### UNIÃO, INTERSEÇÃO e DIFERENÇA Exemplo 1:

Qual o CPF dos funcionários que trabalham no **departamento 5**<br>
**ou / e / mas não**<br>
supervisionam diretamente um funcionário que trabalha no **departamento 5**?

|Expressão|Operação|
|-|-|
|**FUNC_DEPTO_5 ← σ<sub>Dnr=5</sub>(FUNCIONARIO)**|RENOMEAÇÃO, SELEÇÃO|
|**TRABALHA_DEPTO_5 ← π<sub>Cpf</sub>(FUNC_DEPTO_5)**|RENOMEAÇÃO, PROJEÇÃO|
|**SUPERVISIONA_DEPTO_5(Cpf) ← π<sub>Cpf_supervisor</sub>(FUNC_DEPTO_5)**|RENOMEAÇÃO, PROJEÇÃO|
|**RESULT1 ← TRABALHA_DEPTO_5 ∪ SUPERVISIONA_DEPTO_5**|RENOMEAÇÃO, ***UNIÃO***|
|**RESULT2 ← TRABALHA_DEPTO_5 ∩ SUPERVISIONA_DEPTO_5**|RENOMEAÇÃO, ***INTERSEÇÃO***|
|**RESULT3 ← TRABALHA_DEPTO_5 - SUPERVISIONA_DEPTO_5**|RENOMEAÇÃO, ***DIFERENÇA***|

#### UNIÃO, INTERSEÇÃO e DIFERENÇA Exemplo 2:

As operações abaixo estão corretas?<br>
■ FUNCIONARIO ∪ DEPARTAMENTO<br>
■ FUNCIONARIO ∩ DEPARTAMENTO<br>
■ FUNCIONARIO - DEPARTAMENTO

#### UNIÃO, INTERSEÇÃO e DIFERENÇA Exemplo 3:

Qual o CPF dos funcionários que são supervisores e gerentes de departamento?<br>
■ _escreva a consulta em álgebra relacional_...

#### UNIÃO, INTERSEÇÃO e DIFERENÇA Exemplo 4:

Qual o CPF e o nome dos funcionários que são supervisores e gerentes de departamento?<br>
■ _escreva a consulta em álgebra relacional_...

#### UNIÃO, INTERSEÇÃO e DIFERENÇA Exemplo 5:

Qual o maior salário da empresa?<br>
■ _escreva a consulta em álgebra relacional_...

## Atividade (data limite: **08/07/2022 23h59min59s**)

Considere o **esquema lógico** do Banco de Dados Empresa, apresentado no início do presente tópico.

Criar uma _issue_ no projeto https://github.com/plinioleitao/bd-2022-1-bec, com o título "Tópico 11", para responder:  

1. Escreva a seguinte consulta:<br>**Qual o nome dos funcionários que trabalham em mais de um projeto?**

IMPORTANTE:
- Use, NECESSARIAMENTE (SOMENTE), as operações da álgebra relacional apresentadas até o presente tópico.

## Artefatos

1. _Issue_ criada no projeto https://github.com/plinioleitao/bd-2022-1-bec, cujo título é "Tópico 11", para indicar suas reflexões iniciais sobre conceitos da *álgebra relacional*.
