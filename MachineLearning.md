# Parte 1: Machine Learning

A tarefa principal do 'machine learning' é encontrar o melhor **modelo** (descrição de padrões) possível que expresse de
maneira ótima a relação entre as **variáveis independentes** (i.e. número de estudante) e as **variáveis dependentes**
(i.e. ano de entrada na universidade).

A nossa _hipotese_ no exemplo seria:
h(x) = θ0 + θ1 * x

Sendo que θ1 é o parâmetro do modelo, e x é a variável independente.

![](Imagens/machine-learning-1.png)

*Fig.1: Comparações entre modelos*

### Função de custo

A função de custo recebe os parâmetros do modelo e determinar o quão bem o modelo se ajusta aos dados. É ela que
distingue os bons modelos dos maus.

Ela é definida como:

![](Imagens/machine-learning-2.png)

*Fig.2: Função de custo, com o θ0 e o θ1 como os parâmetros do modelo*

### Machine Learning: Otimização

Nós obtemos os melhores valores possiveis minimizando a função de custo. Para isso, temos de calcular as derivadas
parciais da mesma, determinar os seus zeros e através da descida do gradiente, mover-se conforme a direção do gradiente
e o seu learning rate (taxa de aprendizagem/tamanho do passo feito).

#### Exercicio da descida do gradiente

Considere este pequeno dataset. Use a descida do gradiente para encontrar os melhores valores para θ0 e θ1.

- Comece com θ0 = 0 e θ1 = 2
- Use uma taxa de aprendizagem de 0,1

![](Imagens/machine-learning-3.png)

*Fig.3: Dataset para o exercício*

#### Solução

Ainda meto fotos aqui...

### Problemas na classificação (Falsos positivos e falsos negativos)

Às vezes, o modelo não consegue prever corretamente os dados. Isto pode ser devido a um erro de classificação, ou
**falsos positivos** e **falsos negativos**.

- Falsos positivos: quando o modelo classifica um exemplo como positivo, no entanto, é negativo.

- Falsos negativos: quando o modelo classifica um exemplo como negativo, no entanto, é positivo.

#### Exemplo

Suponde que tamos interassados em prever as notas de uma turma. Tipicamente, os alunos que tiram notas boas no
seu primeiro trabalho de casa, tendem a tirar notas boas no resto do ano. No entanto, há sempre exceções. O modelo pode
prever que um aluno que tirou uma nota baixa no seu primeiro trabalho de casa, vai tirar uma nota baixa no resto do ano.
No entanto, este aluno pode ter tido um dia mau, e tirar uma nota alta no resto do ano (falso negativo).

Para evitar estes erros, temos de ajustar o nosso modelo de modo que esses casos expecificos tenham alguma
probabilidade de acontecer, através da função *Sigmoid*.

**POR ACABAR O SLIDER 27**