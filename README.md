# grafos-pontes
Busca por pontes em grafos


Passo a passo

- introdução sobre as redes de distribuição de energia
- perturbações em linhas de transmissão da rede básica (MURILAO)
- introdução sobre os grafos e suas aplicações
---
- gerar um grafo a partir de um arquivo csv ou txt **[OK!]**
- analisar o grafo - centralidades (grau, proximidade e intermediação)
- plotar cada um dos grafos coloridos **[OK!]**
- plotar histograma **[OK!]**
- analisar histograma


## GRAFOS
Um grafo G = (V (G), E(G)) é uma estrutura, consistindo de um conjunto finito e 
não vazio de vértices V =V (G) e um conjunto E = E(G) formado por pares de 
elementos de V , denominado arestas de G .

## REDES COMPLEXAS


## CENTRALIDADE
As medidas de centralidade surgiram da análise em redes sociais, que são um tipo 
específico de rede que se referem a conjunto de pessoas conectadas por relacionamentos 
sociais. Toda rede, social ou não, pode ser representada por um grafo. Cada posição na 
rede corresponde a um vértice no grafo e cada possível relação entre as posições 
corresponde a uma aresta que conecta um par de vértices.
 Intuitivamente, numa rede, os vértices mais centrais são aqueles que a partir dos 
quais podemos atingir qualquer outro com mais facilidade ou rapidez.

## TIPOS DE CENTRALIDADE

diferentes medidas de centralidade que avaliam a 
importância dos nós em uma rede de acordo com sua posição estrutural, dadas em 
função de alguns invariantes do grafo.


### GRAU

A centralidade de grau, assim chamada por ser 
uma função do grau de um vértice, conta o número de arestas incidentes a um vértice do 
grafo.


A concepção mais simples e intuitiva no que diz respeito à centralidade de um 
vértice é o número de contatos diretos que ele possui. Uma pessoa que se encontra em 
uma posição que permite o contato direto com muitos outros é vista pelos demais como 
um canal maior de informações, razão pela qual dizemos ser mais central.




### PROXIMIDADE

 A centralidade de proximidade está relacionada com a distância total de um 
vértice a todos os demais vértices do grafo

é baseada na soma das distâncias de um 
vértice em relação aos demais vértices do grafo. 

### INTERMEDIAÇÃO

 A centralidade 
de intermediação mede quantas geodésicas entre todos os pares de vértices do grafo 
passam através de um determinado vértice.


## 