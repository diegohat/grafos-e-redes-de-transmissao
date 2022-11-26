# Desenvolvimento

A biblioteca Networkx possibilita o cálculo das centralidades e ainda a representação das redes por meio de grafos, onde as barras são representadas pelos vértices enquanto as linhas de transmissão as arestas.

Essa biblioteca é capaz de calcular os métodos de centralidades rapidamente e com pouco esforço computacional, dessa forma a linguagem de programação python é uma alternativa barata e simples para aplicar em problemas de análise de fragilidade do sistema de transmissão de qualquer dimensão.

Quando se analisa a centralidade de grau e intermediação é importante salientar que quando maior a centralidade de grau, maior a quantidade de arestas que se conectam no nó. Pode-se notar que a centralidade de intermediação é influenciada pela quantidade de nós que se conectam ao nó ou seja maior número de arestas em um vértice, maior probabilidade dele atuar como ponte entre dois nós.

A finalidade de analisar a fragilidade da rede é imprescindível para a continuidade da expansão do sistema existente de forma a garantir maior capacidade ao sistema em superar falhas e a utilização de metodologias simples que proporcionam uma análise rápida e efetiva.

Para desenvolver o algoritmo utilizamos a biblioteca Networkx que contém os algoritmos para os cálculos de centralidade. A função betweeness_centrality utiliza do algoritmo de BFS que busca pelo menor caminho entre os pares e realiza a soma desses caminhos que passam pelo nó calculado. Assim, cada um dos nós possui um valor de centralidade para fins de comparação como demonstrado no grafo estudado.

Determinados as somas dos caminhos entre todos os pares possíveis e determinado os valores de centralidade, esses valores são normalizados e comparados em um histograma para melhor visualização.

## Busca em Largura (BFS)

Um algoritmo de busca é um algoritmo que percorre um grafo andando pelos arcos de um vértice a outro.  Depois de visitar a ponta inicial de um arco, o algoritmo percorre o arco e visita sua ponta final.  Cada arco é percorrido no máximo uma vez.

Há muitas maneiras de organizar uma busca.  Cada estratégia de busca é caracterizada pela ordem em que os vértices são visitados.   Este capítulo introduz a busca em largura (= breadth-first search), ou busca BFS.  Essa estratégia está intimamente relacionada com os conceitos de distância e caminho mínimo.

### Algoritmo de Busca em Largura

A busca em largura começa por um vértice, digamos s, especificado pelo usuário.  O algoritmo visita s, depois visita todos os vizinhos de s, depois todos os vizinhos dos vizinhos, e assim por diante.

O algoritmo numera os vértices, em sequência, na ordem em que eles são descobertos (ou seja, visitados pela primeira vez).  Para fazer isso, o algoritmo usa uma fila (= queue) de vértices.  No começo de cada iteração, a fila contém vértices que já foram numerados mas têm vizinhos ainda não numerados.  O processo iterativo consiste no seguinte:

enquanto a fila não estiver vazia retire um vértice v da fila para cada vizinho w de v.
se w não está numerado então numere w.
ponha w na fila.
No começo da primeira iteração, a fila contém o vértice s, com número 0, e nada mais.

![BFS](https://miro.medium.com/max/828/1*alzgv-wAG6KyCbEW4Q1YFg.png)



