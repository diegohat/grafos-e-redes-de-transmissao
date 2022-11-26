# Calculo Centralidades

O cálculo de centralidade no campo da teoria dos grafos e da análise de redes, <b> centralidade</b> é uma medida de importância de um vértice em um grafo.
Existem diferentes tipos de medidas de centralidade de um vértice num grafo que determinam a importância relativa, que permitem, por exemplo, estimar o quanto uma pessoa é influente dentro de uma rede social, o quão é importante uma sala dentro de um edifício e como é bem utilizada uma estrada dentro de uma rede urbana. Vários conceitos de centralidade foram primeiramente desenvolvidos na análise de redes sociais, e muitos dos termos usados para medir a centralidade refletem a sua origem sociológica

## Centralidade de Grau

Centralidade de grau é definida como o número de ligações incidentes de um vértice. O grau pode ser interpretado como a probabilidade que o vértice tem de receber alguma informação da rede. No caso de uma rede orientada (onde os laços tem direção), define-se duas medidas distintas de centralidade de grau: indegree e outdegree. Indegree é uma contagem do número de ligações direcionadas para o nó e outdegree é o número de ligações que o nó encaminha para outros. 
A centralidade de grau de um vértice v, para um dado grafo G:= (V, E) com | V | vértices e | E | arestas, é definido como: 

![image](https://user-images.githubusercontent.com/54191675/204041960-912a8ded-e9e9-49a2-8649-2454f5020e6f.png)

Calculando a centralidade de grau para todos os nós não grafo ![image](https://user-images.githubusercontent.com/54191675/204042081-fd70178f-7ecd-4fcd-9eec-ae926db84ae8.png)em representação da densa matriz de adjacência do grafo, e para as arestas tem ![image](https://user-images.githubusercontent.com/54191675/204042119-c413feb0-0c53-4064-9b57-24c34156e1bb.png) numa representação de uma matriz dispersa. 
 

Por vezes, o interesse está em descobrir a centralidade de um grafo dentro de um grafo. A definição da centralidade no nível do nó pode ser estendida para o grafo inteiro. Deixemos v* ser o nó com maior centralidade de grau em Deixemos X := ( Y , Z ) seja o Y nó conectado ao grafo que maximiza a seguinte quantidade (Com y∗ sendo o nó com maior grau de centralidade X): 

![image](https://user-images.githubusercontent.com/54191675/204042274-67b3a000-ebbb-4a85-93c5-2d67c4de11b7.png)

Analogamente, o grau de centralidade do grafo G é: 

![image](https://user-images.githubusercontent.com/54191675/204042292-183a8558-df4f-4fa8-9ecf-679d9514700d.png)

O valor de H é maximizado quando o grafo X contém um nó central ao qual todos os outros nós são ligados (um grafo em estrela), e neste caso  H = ( n − 1 ) ( n − 2 ).

Exemplo de diferentes centralidades de grau, sendo os vértices de cor mais quente(vermelho) os vértices que possuem maior grau e vértices de cor mais fria os que possuem menor grau.

![image](https://user-images.githubusercontent.com/54191675/204042992-f824b310-cd5d-4129-ab7f-f90ce9a8b0b6.png)

## Centralidade de Proximidade

Em grafos conectados existe uma distância natural métrica entre todos os pares de nós, definido pelo comprimento de seus caminhos mais curtos. O afastamento de um nó s é definido como a soma de suas distâncias para todos os outros nós, e sua proximidade é definida como o inverso do afastamento.

Na definição clássica de centralidade de proximidade, a disseminação de informações é modelada através da utilização dos caminhos mais curtos. Este modelo pode não ser o mais realista de todos os tipos de cenários de comunicação. Assim, as definições relacionadas foram discutidas para medir proximidade, como a centralidade de proximidade de caminhos aleatórios introduzida por Noh e Rieger (2004). Mede a velocidade com que as mensagens aleatórias chegam a um vértice de fora da rede, digamos que é uma espécie de versão aleatória das mensagens da centralidade de proximidade

Exemplo de Deixemos diferentes centralidades de Proximidade, sendo os vértices de cor mais quente(vermelho) os vértices que possuem maior grau e vértices de cor mais fria os que possuem menor grau.

![image](https://user-images.githubusercontent.com/54191675/204043385-41987a7d-0c11-47e2-938b-d0f9efd263f1.png)

## Centralidade de Intermediação

Centralidade de intermediação quantifica o número de vezes que um nó age como ponte ao longo do caminho mais curto entre dois outros nós. Foi introduzido por Linton Freeman como uma medida para quantificar o controlo de um ser humano sobre a comunicação entre outros seres humanos numa rede social. 
A intermediação de um vértice v num grafo G := ( V , E ) com V vértices é calculado como se segue:

- 1. Para cada par de vértices (s,t), calcular os caminhos mais curtos entre eles. 
- 2. Para cada par de vértices (s,t), determinar a fração de caminhos mais curtos que passam através do vértice em questão (neste caso, vértice v ). 
- 3. Somar esta fração de todos os pares de vértices (s,t). 

De forma mais compacta a intermediação pode ser representada como:

![image](https://user-images.githubusercontent.com/54191675/204044286-288bc9d6-b7b5-4950-b19a-a8193c75bb7e.png)

Onde, ![image](https://user-images.githubusercontent.com/54191675/204044728-3245dd01-2d5e-47b8-be85-ef729d1b9f6f.png)
 é o número total de caminhos curtos desde o nó s ao nó t  e ![image](https://user-images.githubusercontent.com/54191675/204044810-95737296-94cc-4ea1-8efe-f8719594b2f7.png)
 é o número desses caminhos que passam por v. A intermediação pode ser normalizada ao ser dividida pelo número de pares de vértices não incluindo v, que para grafos diretos é ( n − 1 ) ( n − 2 )  e para grafos indiretos é ( n − 1 ) ( n − 2 ) / 2 . por exemplo, um grafo indireto em estrela, o vértice central (que está contido em cada caminho mais curto possível) teria uma intermediação de ( n − 1 ) ( n − 2 ) / 2  (1, se normalizado) enquanto as folhas (as quais não estão presentes em nenhum caminhos mais curtos) teria uma intermediação de 0. 

Do ponto de vista de cálculo, tanto a centralidade de intermediação como a de proximidade de todos os vértices de um grafo envolvem o cálculo dos caminhos mais curtos entre todos os pares de vértices de um grafo, que requer um tempo ![image](https://user-images.githubusercontent.com/54191675/204044962-737d4ca4-188d-4942-b23b-fb01b8144382.png) com o algoritmo de Floyd-Warshall.No entanto, em grafos dispersos, o algoritmo de Johnson pode ser mais eficiente, tendo tempo ![image](https://user-images.githubusercontent.com/54191675/204045013-76e43980-295c-4099-8bdf-27b8f2ae017f.png)
. Normalmente, estes algoritmos assumem que os grafos estão sem direção e conectados com a garantia de ciclos e arestas múltiplas. Quando se lidar especificamente com grafos de rede, os grafos estão sem ciclos ou múltiplas arestas para manter relacionamentos simples (onde as arestas representam as ligações entre duas pessoas ou vértices). Neste caso, utilizando o algoritmo de Brandes vai dividir as pontuações finais da centralidade por 2 e contabilizar cada caminho mais curto duas vezes.

Exemplo de diferentes centralidades de Intermediação, sendo os vértices de cor mais quente(vermelho) os vértices que possuem maior grau e vértices de cor mais fria os que possuem menor grau.

![image](https://user-images.githubusercontent.com/54191675/204043618-21d4d602-ebbb-45b2-abe2-75e6b86c4441.png)
	
