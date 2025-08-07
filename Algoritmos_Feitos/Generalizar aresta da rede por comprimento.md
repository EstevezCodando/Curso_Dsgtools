# Módulo 4: Provedor de Algoritmos - Generalização

## Algoritmo: Generalizar Arestas da Rede por Comprimento

## 1. Introdução

O algoritmo **Generalizar Arestas da Rede por Comprimento** permite a simplificação de redes geométricas (como drenagem ou malha viária) ao eliminar arestas com comprimento inferior a um valor mínimo especificado. Esse processo é feito considerando restrições espaciais (pontos, linhas e polígonos) que evitam a remoção de conexões relevantes.

> 💡 *Dica:* Ideal para simplificar redes muito detalhadas em escalas pequenas, preservando conexões essenciais.

---

## 2. Parâmetros de Entrada

| Parâmetro                            | Descrição                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------- |
| Camada de rede                       | Camada vetorial de linhas que representa a rede                          |
| Tamanho mínimo                       | Comprimento mínimo das arestas que devem ser mantidas                    |
| Camadas de restrição (ponto)         | Elementos pontuais que impedem a remoção de arestas conectadas           |
| Camadas de restrição (linha)         | Elementos lineares usados como restrição                                 |
| Camadas de restrição (polígono)      | Camadas poligonais de restrição espacial                                 |
| Camada de referência                 | Camada poligonal usada como subdivisão espacial (opcional)               |
| Executar agrupando por partição      | Divide a camada de referência em regiões menores para processamento paralelo |
| Método                               | Define se a feição será removida ou apenas selecionada (ver abaixo)      |

### Opções do parâmetro “Método”

| Valor | Método                                                                 |
| ----- | ---------------------------------------------------------------------- |
| 0     | Remover feições da camada de entrada                                   |
| 1     | Modificar a seleção atual criando nova seleção                         |
| 2     | Adicionar à seleção atual                                              |
| 3     | Selecionar dentro da seleção atual                                     |
| 4     | Remover da seleção atual                                               |

### Interface de Parâmetros

A imagem abaixo ilustra a interface do algoritmo no QGIS, com os parâmetros a serem preenchidos pelo usuário.

![Interface do algoritmo](assets/modulo-04/img-config-generalize-network-length.png)
*Figura 4.8 – Interface do algoritmo "Generalizar Arestas da Rede por Comprimento".*

---

## 3. Fluxo Operacional

1. Abrir o QGIS e carregar o plugin DSGTools
2. Acessar o algoritmo no provedor DSGTools: *generalizenetworkedgeswithlengthalgorithm*
3. Selecionar a camada de rede e definir o tamanho mínimo
4. Opcionalmente adicionar restrições espaciais e camada de partição
5. Escolher o método desejado (seleção ou remoção)
6. Executar o algoritmo e visualizar os resultados

---

## 4. Funcionamento

O algoritmo funciona por meio da construção de um grafo bidirecional da rede, utilizando a biblioteca *networkx*. A partir desse grafo, são identificadas as conexões que podem ser removidas com base no comprimento mínimo e nas restrições fornecidas. Caso uma camada de referência seja informada com a opção de particionar habilitada, o processo será dividido em múltiplas regiões e executado em paralelo.

> 💡 *Dica:* Use uma camada de referência como partição espacial para redes grandes — isso acelera a execução.

---

## 5. Saída Esperada

Dependendo do método escolhido:
- A camada de entrada terá feições removidas (modo 0) ou
- Um conjunto de feições será selecionado (modos 1 a 4)

---

## 6. Aplicações Práticas

* Generalização de redes de drenagem para escalas menores
* Redução de ruído topológico em malhas de vias
* Preparação de redes para visualização ou exportação
* Preservação de conexões relevantes via camadas de restrição

---

## 7. Resumo

* Algoritmo para generalização topológica baseada em grafo
* Permite controle por restrições espaciais e regionalização
* Otimizado com execução paralela por partição geográfica
* Flexível: seleção ou exclusão direta das arestas generalizadas

> 🔹 *Recomendado:* Trabalhar com redes previamente indexadas para acelerar o processamento.

> ⚠️ *Atenção:* É necessário ter a biblioteca `networkx` instalada no ambiente Python do QGIS.
