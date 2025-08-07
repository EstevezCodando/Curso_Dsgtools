
# Módulo 4: Provedor de Algoritmos - QA Tools: Topological Processes

## Algoritmo: Topological Clean Linestrings

## 1. Introdução

O algoritmo `Topological Clean Linestrings` realiza a limpeza topológica de camadas vetoriais do tipo linha, corrigindo sobreposições e lacunas entre feições, de acordo com os parâmetros de tolerância espacial definidos pelo usuário.

É ideal para harmonizar e refinar redes lineares (como hidrografia e vias) em bases cartográficas que exigem alta precisão e integridade topológica.

---

## 2. Parâmetros de Entrada

| Parâmetro                     | Descrição                                                                 |
|------------------------------|---------------------------------------------------------------------------|
| `Linestring Layers`          | Lista de camadas vetoriais de linhas a serem limpas topologicamente       |
| `Process only selected features` | Se ativado, o algoritmo atuará apenas nas feições selecionadas            |
| `Snap radius`                | Raio de ajuste para aproximação entre vértices de linhas (unidades da camada) |
| `Minimum area`               | Área mínima para remoção de pequenos polígonos residuais gerados na limpeza |
| `Geographic Bounds Layer`    | Camada de polígono usada como limite geográfico para o processamento       |

### Interface de Parâmetros

![Interface de Parâmetros](./assets/modulo-04/img-interface-topo-clean-lines.png)
*Figura 4.x – Interface do algoritmo "Topological Clean Linestrings".*

> **🔎 Observação:** A tolerância deve ser cuidadosamente definida para evitar modificações excessivas ou perda de dados.

---

## 3. Funcionamento

O algoritmo unifica as camadas de linhas fornecidas, aplicando um processo de "snap" para unir vértices próximos dentro do raio especificado. Ele também remove pequenas feições indesejadas com área inferior ao valor definido.

Após a limpeza, são sinalizados dois tipos principais de problemas:

- **Gaps**: lacunas onde nenhuma geometria foi mantida
- **Overlaps**: sobreposições entre feições da mesma camada

Esses problemas são representados por flags na saída, facilitando a posterior correção manual ou automatizada.

---

## 4. Saída Esperada

* Camada de saída contendo pontos com flags para gaps e overlaps
* Atributos indicando o tipo de problema identificado
* Geometria das feições preservada e harmonizada com base na tolerância definida

![Exemplo de Saída](./assets/modulo-04/img-result-topo-clean-lines.png)
*Figura 4.x – Exemplo de flags indicando problemas topológicos detectados.*

---

## 5. Aplicações Práticas

* Limpeza e alinhamento de redes hidrográficas e viárias
* Preparação de dados para análise de conectividade e rede
* Verificação de consistência topológica em bases colaborativas
* Integração de camadas provenientes de fontes distintas

---

## 6. Resumo

* Realiza limpeza topológica de linhas com base em raio de snap e área mínima
* Detecta e sinaliza gaps e overlaps entre feições
* Ideal para refinar dados vetoriais antes de análises ou integração

> **ℹ️ Dica:** Combine este algoritmo com validadores geométricos para garantir uma base cartográfica robusta e sem erros críticos.
