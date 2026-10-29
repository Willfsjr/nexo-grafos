# Nexo · Laboratório de Grafos

**Aluno: WillianFerreira**

Aplicativo educacional para construir e visualizar grafos ponderados, gerar uma **Árvore Geradora Mínima (AGM)** com **Prim** ou **Kruskal** e encontrar **caminhos mais curtos** com **Dijkstra**.

O objetivo é ajudar a compreender as decisões dos algoritmos, mostrando as conexões escolhidas, os pesos e a execução passo a passo.

## Como abrir

1. Baixe o repositório pelo botão **Code → Download ZIP**, ou baixe o arquivo `nexo-grafos.html`.
2. Se usar o ZIP, extraia os arquivos.
3. Abra `nexo-grafos.html` em um navegador atualizado.

O aplicativo funciona **sem internet**, sem instalação e sem servidor. Todo o HTML, CSS e JavaScript está em um único arquivo.

## O que o aplicativo faz

- Cria vértices e arestas com pesos.
- Permite trabalhar com grafos direcionados ou não direcionados.
- Permite arrastar vértices e organizar o desenho em círculo.
- Edita pesos e exclui vértices ou arestas.
- Calcula AGM com Prim e Kruskal.
- Gera uma floresta geradora mínima quando o grafo é desconectado.
- Calcula as menores distâncias a partir de uma origem com Dijkstra e destaca a rota até o destino.
- Mostra o peso da solução, as arestas escolhidas, as distâncias e os antecessores.
- Permite avançar, voltar e reproduzir automaticamente as etapas.
- Importa e exporta grafos em JSON.
- Salva o grafo automaticamente no navegador, quando o armazenamento está disponível.
- Inclui exemplos e um guia de conceitos e uso.

## Algoritmos disponíveis

| Algoritmo | Finalidade | Como funciona | Condições |
| --- | --- | --- | --- |
| **Prim** | Gerar uma AGM | Parte de um vértice e acrescenta a aresta mais leve que conecta a árvore a um vértice ainda não incluído. | Grafo não direcionado; aceita pesos negativos, zero ou positivos. |
| **Kruskal** | Gerar uma AGM | Ordena as arestas por peso e seleciona as que unem componentes distintos, sem formar ciclos. | Grafo não direcionado; aceita pesos negativos, zero ou positivos. |
| **Dijkstra** | Encontrar caminhos mais curtos | Fixa o vértice ainda não visitado com menor distância e atualiza as estimativas dos vizinhos por relaxamento. | Grafo direcionado ou não direcionado; exige pesos não negativos. |

Uma AGM conecta todos os vértices de um grafo conectado sem formar ciclos e com a menor soma dos pesos. Para **n vértices**, ela possui **n − 1 arestas**. Empates podem produzir árvores diferentes com o mesmo peso mínimo.

Se o grafo for desconectado, não existe uma AGM que conecte todos os seus vértices. Nesse caso, Prim e Kruskal retornam uma **floresta geradora mínima**, incluindo os vértices isolados.

Em Dijkstra, **∞** indica que o vértice não pode ser alcançado a partir da origem. A tabela mostra as distâncias finais para todos os vértices; o desenho final destaca o caminho até o destino escolhido.

## Como usar

1. Carregue um exemplo ou clique em **Limpar** para construir um grafo.
2. Adicione os vértices pelo formulário ou pelo modo **Vértice**.
3. Adicione arestas informando origem, destino e peso. No modo **Aresta**, também é possível clicar nos dois vértices para conectá-los.
4. Escolha o algoritmo. Em Prim, selecione o vértice inicial. Em Dijkstra, selecione origem e destino.
5. Clique em **Gerar árvore mínima** ou **Encontrar menor caminho**.
6. Consulte as abas **Resultado**, **Passo a passo** e **Dados do grafo**.
7. Use as setas e o botão de reprodução para acompanhar cada decisão.

Para alterar um peso, clique no rótulo da aresta ou use a aba **Dados do grafo**. Para excluir um elemento, selecione-o e clique em **Excluir**.

As cores do desenho indicam:

- **Cinza:** arestas do grafo original.
- **Verde:** arestas da solução ou selecionadas até a etapa exibida.
- **Laranja tracejado:** aresta em análise.

## Exemplos incluídos

| Exemplo | Resultado esperado |
| --- | --- |
| **Rede de conexões** | 7 vértices e 11 arestas. Prim e Kruskal encontram uma AGM de peso **18**, com **6 arestas**. |
| **Rotas direcionadas** | De **S** até **T**, Dijkstra encontra **S → B → A → C → T**, com distância **7**. |
| **Grafo desconectado** | 6 vértices e 3 componentes. A floresta mínima tem peso **6**, com **3 arestas**; F permanece isolado. |

## Limites e cuidados

- Até **30 vértices**, com nomes únicos de **1 a 8 caracteres**.
- Pesos entre **−1.000.000.000 e 1.000.000.000**.
- Sem laços ou arestas duplicadas no mesmo sentido.
- Dijkstra bloqueia a execução se houver alguma aresta de peso negativo.
- O salvamento automático é específico do navegador e pode não estar disponível em todos os ambientes. Use **Exportar grafo** para guardar ou compartilhar seus dados.

## Tecnologias e arquivos

O projeto utiliza **HTML, CSS, JavaScript e SVG**, sem bibliotecas externas.

- [nexo-grafos.html](nexo-grafos.html): aplicativo completo e código-fonte.
- [README.md](README.md): descrição e instruções de uso.

## Referência conceitual

*Algoritmos em Grafos*, Projeto de Algoritmos, capítulo 7, seções 7.8 e 7.9. Transparências elaboradas por Charles Ornelas Almeida, Israel Guerra e Nivio Ziviani, com atualização indicada de 24/09/2010.

Os grafos dos exemplos do aplicativo são próprios.
