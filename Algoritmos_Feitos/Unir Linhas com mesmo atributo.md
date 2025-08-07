# Módulo 4: Provedor de Algoritmos - QA Tools: Manipulação de Linhas

## Algoritmo: Unir Linhas com Mesmo Conjunto de Atributos

## 1. Introdução

O algoritmo *Unir Linhas com Mesmo Conjunto de Atributos* permite identificar e mesclar segmentos de linha adjacentes que compartilham o mesmo conjunto de atributos, respeitando restrições espaciais como pontos de controle, linhas limitantes e fronteiras geográficas.

> 💡 *Dica:* Esse processo é especialmente útil para generalizar redes lineares como hidrografia, estradas e outras infraestruturas, consolidando geometrias redundantes.

---

## 2. Parâmetros de Entrada

| Parâmetro                          | Descrição                                                                 |
| ---------------------------------- | ------------------------------------------------------------------------- |
| Camada de entrada                  | Camada vetorial do tipo linha a ser processada                            |
| Processar apenas feições selecionadas | Limita o processamento às feições previamente selecionadas               |
| Campos a ignorar                  | Lista de campos que devem ser desconsiderados na comparação de atributos  |
| Ignorar campos virtuais           | Desconsidera campos calculados ou temporários                             |
| Ignorar campos de chaves primárias| Ignora campos que identificam unicamente as feições                       |
| Permitir linhas fechadas na saída | Autoriza união de linhas formando anéis fechados                          |
| Camadas de filtro de pontos       | Conjunto de camadas de pontos que restringem a união                      |
| Camadas de filtro de linhas       | Conjunto de camadas de linhas que impedem a fusão                         |
| Limite geográfico                 | Polígono que limita espacialmente a área de processamento                 |

### Interface de Parâmetros

> ⚠️ *Atenção:* Para o correto funcionamento do algoritmo:
> 
> - A biblioteca `networkx` deve estar instalada no ambiente Python.
> - A camada de entrada precisa estar em modo de edição.
> - Linhas devem ter conectividade compatível (nó-final com nó-inicial) para serem unidas.

---

## 3. Fluxo Operacional

1. Abrir o QGIS com o plugin DSGTools ativado
2. Localizar o algoritmo “Unir Linhas com Mesmo Conjunto de Atributos” (Atalho: `mergelineswithsameattributeset`)
3. Escolher a camada de entrada e os parâmetros opcionais (filtros, atributos a ignorar, etc.)
4. Executar o algoritmo
5. Verificar a atualização da camada original com feições fundidas

---

## 4. Funcionamento

O algoritmo constrói um grafo topológico com os vértices das linhas e avalia conectividade e atributos para decidir quais feições podem ser fundidas. A fusão respeita restrições espaciais (como limites e nós de controle), garantindo integridade lógica da rede.

A biblioteca `networkx` é usada para detectar caminhos conectados entre feições com atributos equivalentes. A fusão só ocorre quando os critérios de geometria e atributo são compatíveis.

---

## 5. Saída Esperada

* A camada de entrada será editada diretamente, substituindo feições individuais por segmentos unidos.
* As geometrias resultantes respeitam conectividade, atributos comuns e restrições impostas.
* Linhas duplicadas ou segmentadas indevidamente são reduzidas, mantendo consistência topológica.

---

## 6. Aplicações Práticas

* Consolidação de segmentos de estradas, rios, redes elétricas e drenagens
* Redução de fragmentação em redes lineares
* Pós-processamento de digitalizações automáticas (onde há muitos trechos quebrados)
* Otimização de análise de conectividade e trajetos em redes

---

## 7. Resumo

* Funde segmentos de linha com atributos comuns
* Respeita restrições espaciais definidas pelo usuário
* Ideal para otimização e limpeza de redes lineares
* Exige `networkx` instalado para funcionamento

> 🔹 *Recomendado:* Usar esse algoritmo após extrações ou divisões de feições para consolidar geometrias.

> ⚠️ *Atenção:* O processo modifica diretamente a camada de entrada. Recomenda-se salvar uma cópia antes da execução.

