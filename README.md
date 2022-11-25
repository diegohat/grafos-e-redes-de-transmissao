# grafos-pontes
Busca por pontes em grafos


Passo a passo

- introdução sobre as redes de distribuição de energia
- perturbações em linhas de transmissão da rede básica (MURILAO)
- metodo de adicao de arestas (PAIVA)
- introdução sobre os grafos e suas aplicações
---
- gerar um grafo a partir de um arquivo csv ou txt **[OK!]**
- analisar o grafo - centralidades (grau, proximidade e intermediação)
- plotar cada um dos grafos coloridos
- plotar histograma
- analisar histograma



#prototipo
## Introdução
 Esse trabalho tem como objetivo aplicar as estruturas grafos para solucionar um problema real qualquer, o problema escolhido foi de analise de estabilidade em linhas de transmissao de energia eletrica, com o cálculo de centralidades para mesurar a importancia que o barramento tem no sistema e garantir a boa serventia perante falhas no sistema.
 
 Com o intuito de realizar testes no sistema, permitindo que a seja possivel aplicar em qualquer rede de tramissao de energia elétrica, garantindo maior confiabilidade e diminuição de risco de interrupção no fornecimento de enérgia eletrica.
 
 ## Grafos
 
 Um grafo é uma representação abstrata de um conjunto de objetos e das relaçoes existentes entre eles.
 É definido por um conjunto de nós ou vérticies e pelas ligações ou arestas, que ligam pares de nós. Uma grande variedade de estruturas do mundo real podem ser representadas abstratamente através de grafos. 
 
 ![image](https://user-images.githubusercontent.com/54191675/204011472-abc9d182-bd8f-4513-93a0-73a8b24b9302.png)

### Conceitos de grafos 

Um grafo é descrito por um par (V,E), onde V é o conjunto de vértices e E o conjunto das arestas que ligam pares de vértices. Um grafo pode ser dirigido ou direcionado, se as arestas tiverem uma direção, ou não dirigido, se as arestas não tiverem direção. A figura seguinte ilustra um grafo dirigido. 
 
 ![image](https://user-images.githubusercontent.com/54191675/204011724-35d17008-0239-4c94-9fb0-b693b47b574b.png)

Se as arestas tiverem associado um peso ou custo, o grafo passa a chamar-se de grafo pesado. A figura seguinte ilustra um grafo pesado não dirigido. 

![image](https://user-images.githubusercontent.com/54191675/204011774-377a1639-42a8-4159-a1ca-e05e0c0d3579.png)

Os nós podem ser de diferente tipos, representados por cores ou etiquetas. Nesse caso, o grafo diz-se colorido. A figura seguinte ilustra um grafo colorido não dirigido. 

![image](https://user-images.githubusercontent.com/54191675/204011944-e17f9f97-42c6-4777-b68e-6ecfc275bbff.png)

Quando apenas é admitida no máximo uma aresta entre dois nós, diz-se que o grafo é simples.

### Grafos e a Ciência de Computadores 

Com a enorme utilidade dos grafos, existe toda uma área de Ciência de Computadores dedicada ao seu estudo e são inúmeros e muito importantes os algoritmos que manipulam grafos. Um exemplo é o Algoritmo de Dijkstra, que encontra o caminho mais curto entre um nó e todos os outros nós, num grafo pesado. Existem muitos outros algoritmos para outras tarefas tais como maximizar o fluxo entre nós ou encontrar a árvore mínima de suporte. 

Do ponto de vista da Programação, um grafo é uma estrutura de dados e existem duas maneiras base de o implementar na prática:

- <b>Matriz de Adjacências:</b> uma matriz de V por V células, onde a célula na linha i e coluna j nos dá informação sobre a ligação entre os nós i e j. Por exemplo, se o grafo não for pesado, a célula podia conter o valor verdadeiro (ou um) quando existisse uma ligação entre i e j e o valor falso (ou zero) quando tal não acontecesse. Se o grafo for pesado, cada célula pode conter um número representando o peso da aresta. A figura seguinte ilustra um grafo não dirigido e a sua correspondente matriz de adjacências. 

![image](https://user-images.githubusercontent.com/54191675/204012590-29255987-c010-438f-9995-96b122603d70.png)

- <b>Lista de Adjacências:</b> um vetor de listas onde a posição i do vetor contém uma lista dos nós aos quais o nó i se encontra ligado. Se o grafo for pesado, cada elemento da lista contém também o peso da ligação. A figura seguinte ilustra um grafo não dirigido e a sua correspondente lista de adjacências.

![image](https://user-images.githubusercontent.com/54191675/204012842-41f77227-b335-4c33-b5c3-53ceddc77a9e.png)


A matriz permite verificar em tempo constante se uma dada ligação existe ou não. Por oposição, no caso da lista, tal não acontece e é necessário percorrer a lista para saber se um dado nó está ou não ligado. Em contrapartida, se for necessário percorrer todos os nós ligados a um dado nó, a lista é mais eficiente, pois permite percorrer apenas os nós ligados, e não andar a percorrer toda uma linha da matriz, verificando se a ligação existe ou não. 

## Redes de Distribuição de Energia

O sistemas elétricos de potência têm a função essencial de fonercer energia elétrica aos usuários, com qualidade e no instante em que for solicitada e esses sistemas podem ser divididos em três grandes blocos:

- <b>Geração:</b> que perfaz a função de converter alfuma forma de energia em energia elétrica.

- <b>Transmissão:</b>  que é responsavel pelo transporte de energia elétrica dos centros de produção aos de consumo.

- <b> Distribuição: </b> que distribui energia elétrica recebida do sistema de transmissão aos grandes, médios e pequenos consumidores.

E um elemento chave desses sistemas, uma parte comum deles, os transformadores são maquinas elétricas estáticas que têm finalidade de aumentar ou abaixar a tensão e a corrente eletricas por indução eletromagnética. Os trnasformadores desempenham papel preponderante nos sistemas de distribuição, para compatibilizar os níveis de tensão fornecidos pela concessionária de energia local, os quais são elevados e perigosos, para aqueles apropriados à utilização com segurança em empreendimentos industriais, comerciais e residenciais.

![image](https://user-images.githubusercontent.com/54191675/204018590-f8823bfa-a646-4982-bfdf-48d3a61ba8f5.png)

## Confiabilidade

O cenario atual no Brasil, com a presença de um órgão governamental regulador do setor, exige cada vez mais qualidade das empressas concessionária que distribuem energia elétrica e com orçamentos limitados das empresas, no atual momento econômico, fica essencial o desenvolvimento de métodos de análise otimizada para que indique pontos priotarios de investimento no sistema elétrico.

Uma eventual falha em alguma linha de transmissão que, dependendo do grau de contribuição para o sistema, pode provocar um blecaute, deixando milhares de consumidores sem energia elétrica. Como em Amapá em 2020 que uma interrupção no fornecimento deixou cerca de 800 mil pessoas sem energia elétrica por volta de 20 dias e em 2018, uma falha na linha de transmissão ligada à usina de Belo Monte afetou 70 milhões de pessoas com um blecaute.
Propondo-se evitar tais casos, o estudo de fragilidades em linhas de transmissão se destaca ja que o impacto causado por uma eventual falha dessa pode resultar em perdas ecônomicas e desconforto para todos consumidores.




O transporte de energia das usinas geradoras até a unidade de consumo no brasil ja se depara com o desafio territorial, sendo um territorio muito extenso e possui diversos topologias de terrenos. E as linhas de transmissão estao expostas a diversos fatores que podem provocar falhas nos sistemas, como queimadas, falha em equipamento, ventos fortes, descargas atmosféricas e falha humana podendo interroper o fluxo de energia. 

![image](https://user-images.githubusercontent.com/54191675/204029425-2b727213-471f-46c4-9e4d-23051dbb4d16.png)


## Calculo Centralidades

O calculo de centralidade no campo da teoria dos grafos e da análise de redes, <b> centralidade</b> é uma medida de importancia de um verice em um grafo.
Existem diferentes tipos de medidas de centralidade de um vértice num grafo que determinam a importância relativa, que permitem, por exemplo, estimar o quanto uma pessoa é influente dentro de uma rede social, o quão é importante uma sala dentro de um edifício e como é bem utilizada uma estrada dentro de uma rede urbana. Vários conceitos de centralidade foram primeiramente desenvolvidos na análise de redes sociais, e muitos dos termos usados para medir a centralidade refletem a sua origem sociológica

### Centralidade de Grau

Centralidade de grau é definida como o número de ligações incidentes de um vértice. O grau pode ser interpretado como a probabilidade que o vértice tem de receber alguma informação da rede. No caso de uma rede orientada (onde os laços tem direção), define-se duas medidas distintas de centralidade de grau: indegree e outdegree. Indegree é uma contagem do número de ligações direcionadas para o nó e outdegree é o número de ligações que o nó encaminha para outros. 
A centralidade de grau de um vértice v , para um dado grafo G := ( V , E )  com | V | vértices e | E |  arestas, é definido como: 

![image](https://user-images.githubusercontent.com/54191675/204041960-912a8ded-e9e9-49a2-8649-2454f5020e6f.png)

Calculando a centralidade de grau para todos os nós num grafo ![image](https://user-images.githubusercontent.com/54191675/204042081-fd70178f-7ecd-4fcd-9eec-ae926db84ae8.png)em representação da densa matriz de adjacência do grafo, e para as arestas tem ![image](https://user-images.githubusercontent.com/54191675/204042119-c413feb0-0c53-4064-9b57-24c34156e1bb.png) numa representação de uma matriz dispersa. 
 

Por vezes, o interesse está em descobrir a centralidade de um grafo dentro de um grafo. A definição da centralidade no nível do nó pode ser estendida para o grafo inteiro. Deixemos v* ser o nó com maior centralidade de grau em G.Deixemos X := ( Y , Z ) seja o Y nó conectado ao grafo que maximiza a seguinte quantidade (Com y∗ sendo o nó com maior grau de centralidade X): 

![image](https://user-images.githubusercontent.com/54191675/204042274-67b3a000-ebbb-4a85-93c5-2d67c4de11b7.png)

Analogamente, o grau de centralidade do grafo G é: 

![image](https://user-images.githubusercontent.com/54191675/204042292-183a8558-df4f-4fa8-9ecf-679d9514700d.png)

O valor de H é maximizado quando o grafo X contém um nó central ao qual todos os outros nós são ligados (um grafo em estrela), e neste caso  H = ( n − 1 ) ( n − 2 ).

Exemplo de de diferentes centralidades de grau, sendo os vertices de cor mais quente(vermelho) os vertices que possuiem maior grau e vertices de cor mais fria os que possuem menor grau.

![image](https://user-images.githubusercontent.com/54191675/204042992-f824b310-cd5d-4129-ab7f-f90ce9a8b0b6.png)


### Centralidade de Proximidade

Em grafos conectados existe uma distância natural métrica entre todos os pares de nós, definido pelo comprimento de seus caminhos mais curtos. O afastamento de um nó s é definido como a soma de suas distâncias para todos os outros nós, e sua proximidade é definida como o inverso do afastamento.

Na definição clássica de centralidade de proximidade, a disseminação de informações é modelada através da utilização dos caminhos mais curtos. Este modelo pode não ser o mais realista de todos os tipos de cenários de comunicação. Assim, as definições relacionadas foram discutidas para medir proximidade, como a centralidade de proximidade de caminhos aleatórios introduzida por Noh e Rieger (2004). Mede a velocidade com que as mensagens aleatórias chegam a um vértice de fora da rede, digamos que é uma espécie de versão aleatória das mensagens da centralidade de proximidade

Exemplo de de diferentes centralidades de Proximidade, sendo os vertices de cor mais quente(vermelho) os vertices que possuiem maior grau e vertices de cor mais fria os que possuem menor grau.

![image](https://user-images.githubusercontent.com/54191675/204043385-41987a7d-0c11-47e2-938b-d0f9efd263f1.png)

### Centralidade de Intermediação

Centralidade de intermediação quantifica o número de vezes que um nó age como ponte ao longo do caminho mais curto entre dois outros nós. Foi introduzido por Linton Freeman como uma medida para quantificar o controlo de um ser humano sobre a comunicação entre outros seres humanos numa rede social. 
A intermediação de um vértice v num grafo G := ( V , E ) com V vértices é calculado como se segue:

- 1. Para cada par de vértices (s,t), calcular os caminhos mais curtos entre eles. 
- 2. Para cada par de vértices (s,t), determinar a fração de caminhos mais curtos que passam através do vértice em questão (neste caso, vértice v ). 
- 3. Somar esta fração de todos os pares de vértices (s,t). 

De forma mais compacta a intermediação pode ser representada como:

![image](https://user-images.githubusercontent.com/54191675/204044286-288bc9d6-b7b5-4950-b19a-a8193c75bb7e.png)

Onde, ![image](https://user-images.githubusercontent.com/54191675/204044728-3245dd01-2d5e-47b8-be85-ef729d1b9f6f.png)
 é o número total de caminhos curtos desde o nó s ao nó t  e ![image](https://user-images.githubusercontent.com/54191675/204044810-95737296-94cc-4ea1-8efe-f8719594b2f7.png)
 é o número desses caminhos que passam por v. A intermediação pode ser normalizada ao ser dividida pelo número de pares de vértices não incluindo v, que para grafos diretos é ( n − 1 ) ( n − 2 )  e para grafos indiretos é ( n − 1 ) ( n − 2 ) / 2 . or exemplo, um grafo indireto em estrela, o vértice central (que está contido em cada caminho mais curto possível) teria uma intermediação de ( n − 1 ) ( n − 2 ) / 2  (1, se normalizado) enquanto as folhas (as quais não estão presentes em nenhum caminhos mais curtos) teria uma intermediação de 0. 


Do ponto de vista de cálculo, tanto a centralidade de intermediação como a de proximidade de todos os vértices de um grafo envolvem o cálculo dos caminhos mais curtos entre todos os pares de vértices de um grafo, que requer um tempo ![image](https://user-images.githubusercontent.com/54191675/204044962-737d4ca4-188d-4942-b23b-fb01b8144382.png) com o algoritmo de Floyd-Warshall.No entanto, em grafos dispersos, o algoritmo de Johnson pode ser mais eficiente, tendo tempo ![image](https://user-images.githubusercontent.com/54191675/204045013-76e43980-295c-4099-8bdf-27b8f2ae017f.png)
. Normalmente, estes algoritmos assumem que os grafos estão sem direção e conectados com a garantia de ciclos e arestas múltiplas. Quando se lidar especificamente com grafos de rede, os grafos estão sem ciclos ou múltiplas arestas para manter relacionamentos simples (onde as arestas representam as ligações entre duas pessoas ou vértices). Neste caso, utilizando o algoritmo de Brandes vai dividir as pontuações finais da centralidade por 2 e contabilizar cada caminho mais curto duas vezes.

Exemplo de de diferentes centralidades de Intermediação, sendo os vertices de cor mais quente(vermelho) os vertices que possuiem maior grau e vertices de cor mais fria os que possuem menor grau.

![image](https://user-images.githubusercontent.com/54191675/204043618-21d4d602-ebbb-45b2-abe2-75e6b86c4441.png)

## Metodologia

Inicialmente a ideia era extrair dados das redes IEEE registrados na base de dados do software SINAPgrid, mas o software é pago, então criamos um grafo aleatorio em um arquivo csv para a analise da rede, com calculo das diferentes centralidades.

A blibioteca Networkx possibilita o cálculo das centralidades e ainda a representação das redes por meio de grafos. Dessa forma, a linguagem de programação Python é uma alternativa barata e simples para aplicar em análise de fragilidade do sistema de transmissão de qualquer dimensão.

Quando analisa-se a centralidade de grau e intermediação é importante resaltar que quando a maior centralidade de grau, maior é a quantidade de arestas que se conectam ao nó.E que é a centralidade de intermediação é influenciada pela quantidade de nós que se conectam ao nó, ou seja, quanto maior o número de arestas em um nó, maior probabilidade daquele nó atuar como ponte entre outro dois nós, situação que define a centralidade de intermediação.

- referencias por enquanto 
(https://wikiciencias.casadasciencias.org/wiki/index.php/Grafo)
https://bmcnews.com.br/2021/07/24/crise-hidrica-x-apagao-no-brasil-relembre-os-maiores-blecautes-no-pais/
https://pt.wikipedia.org/wiki/Centralidade
