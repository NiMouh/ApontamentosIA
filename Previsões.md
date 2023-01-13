# Perguntas teóricas
- **Definição de estado, estado inicial, estado objetivo e operadores.**

Um **estado** é uma representa toda a informação relativa á posição atual do agente no ambiente (espaço de estados) numa estrutura de dados.
O **estado inicial** representa toda a informaçao relativa á primeira posição do agente no ambiente.
Alguns estados podem ser denominados **solução ou objetivo**, pois representam uma situação que o agente deseja alcançar.

- **Diferença entre pesquisa informada e não informada.**

Não informadas: não utilizam nenhuma informação adicional sobre o problema.
Informadas: utilizam informação adicional sobre o problema.

- **O que é o gradiente e o learning rate.**

O gradiente é um vetor de derivadas parciais de uma função de perda com relação aos pesos da rede neural. Ele indica a direção e a intensidade da mudança nos pesos que minimizariam a função de perda.

O learning rate é um hiperparâmetro que determina a taxa de aprendizado de uma rede neural. Ele especifica o tamanho do passo a ser dado na direção do gradiente durante a otimização dos pesos. Se o learning rate for muito pequeno, o processo de treinamento levará muito tempo para convergir, mas se for muito grande, pode haver oscilações ou mesmo divergência. Portanto, é importante escolher um learning rate adequado para garantir um bom desempenho da rede neural durante o treinamento.

- **Na otimização diferença entre métodos de construção e métodos de reparação.**

Métodos de construção: começam do zero e vão a construir uma solução iterativamente.
Métodos de reparação: começam num ponto aleatório (com bases periciais) e vão a ajustar os parametros e iterativamente melhorá-los.

- **Definir machine learning ou deep learning.**

A tarefa principal do 'machine learning' é encontrar o melhor modelo (descrição de padrões) possível que expresse de maneira ótima a relação entre as variáveis independentes (i.e. número de estudante) e as variáveis dependentes (i.e. ano de entrada na universidade).
Ao contrário do machine learning, o deep learning usa redes neurais profundas para resolver problemas, isto é, redes neurais com muitas camadas.

- **O que entender por overfitting e underfitting**

Overfitting: O modelo ajusta-se demasiado ao dataset de treino, e não consegue generalizar bem para outros datasets.
Underfitting: O modelo não consegue ajustar-se bem ao dataset de treino, e não consegue generalizar bem para outros datasets.

- **Supervised learning vs Unsupervised learning**

Supervised learning é quando o conjunto de dados de treino inclui rótulos com as respostas corretas para cada exemplo no conjunto. O objetivo é usar os exemplos rotulados para prever as respostas para novos exemplos.

Unsupervised learning é quando o conjunto de dados de treino não inclui rótulos. O objetivo é descobrir padrões nos dados.

# Perguntas práticas
- **Algoritmo A# (fazer em python ou á mão)**
    Sejam

    Q = conjunto de nós a serem pesquisados;
    S = o estado inicial da busca
    Faça:

    Inicialize Q com o nó de busca (S) como única entrada;
    Se Q está vazio, interrompa. Se não, escolha o melhor elemento de Q;
    Se o estado (n) é um objetivo, retorne n;
    (De outro modo) Remova n de Q;
    Encontre os descendentes do estado (n) que não estão em visitados e crie todas as extensões de n para cada descendente;
    Adicione os caminhos estendidos a Q e vá ao passo 2;

- **Dedução/Dedução inversa**
    **DEDUÇÃO**
    Considerando a seguinte base de conhecimento:

    american(P) AND weapon(Q) AND sells(P, Q, R) AND hostile(R) → criminal(P)
    owns(evil_country, t)
    missile(t)
    missile(P) AND owns(evil_country, P) → sells(robert, P, evil_country)
    missile(P) → weapon(P)
    enemy(P, america) → hostile(P)
    enemy(evil_country, america)
    american(robert).
    Prove criminal(robert).

    **R:**
    1. Sabemos que para ser um criminoso têm de acontecer três coisas: ser americano, ter uma arma e vender a arma a um país hostil.
    2. Como sabemos que o robert é americano, temos de saber se ele tem uma arma e vendeu-se a arma a um país hostil. Então sabemos, american(robert) → true, precisamos saber se sells(robert, t,evil_country) → true.
    3. Sabemos que o robert tem uma arma, pois tem um míssil. Sabemos que o robert vendeu a arma a um país hostil, pois o país é o evil_country. Então, missile(t) → weapon(t), owns(evil_country, t) → true, enemy(evil_country, america) → hostile(evil_country) → true.
    4. Então, american(robert) AND weapon(t) AND sells(robert, t, evil_country) AND hostile(evil_country) → criminal( robert) → true.

- **Alfa/Beta Prunning**

    Este é um método de corte que permite reduzir o número de nós a explorar no algoritmo minimax. Este método é baseado na seguinte ideia:
    O alfa representa o valor máximo que o maximizador pode obter garantidamente (é inicializado com −∞).
    O beta representa o valor mínimo que o minimizador pode obter garantidamente (é inicializado com +∞).
    A ideia geral é cortar as ramificações que não precisam de ser exploradas, pois, já sabemos que não vão ser escolhidas.
    Em cada nó em que o alpha é maior ou igual ao beta, podemos cortar a árvore.

- **Algoritmo Minimax alpha-beta pruning (fazer em python ou á mão)**
    ```md
    1. Se a profundidade for 0 ou o nó for um nó terminal (folha), retorna o valor do nó
    2. Caso seja o maximizador a jogar, maximiza o valor
    1. valor = -infinito
    2. Para cada filho do nó
        1. Máximo entre o valor e o valor do filho (agora a jogar é o minimizador)
        2. Alfa = Máximo entre o alfa e o valor
        3. Se o valor for maior ou igual ao beta, corta a árvore
    3. Caso seja o minimizador a jogar, minimiza o valor
        1. valor = infinito
        2. Para cada filho do nó
        1. Mínimo entre o valor e o valor do filho (agora a jogar é o maximizador)
        2. Beta = Mínimo entre o beta e o valor
        3. Se o valor for menor ou igual ao alfa, corta a árvore
    4. Retorna o valor
    ```

CONSEGUIMOS!
