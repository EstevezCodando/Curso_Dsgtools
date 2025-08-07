# Módulo 4: Provedor de Algoritmos - Grid

##  Algoritmo: Create Review Grid (Criar Grade de Revisão)

## 1. Introdução

O algoritmo `Create Review Grid` permite a criação de uma grade regular com base na geometria de uma camada poligonal de entrada. Ele é ideal para subdividir áreas existentes em **blocos (tiles)** com dimensões definidas em unidades do CRS.

> **💡 Dica:** Esse algoritmo é útil em processos de revisão, validação e segmentação de grandes áreas, especialmente no contexto de produção cartográfica.

---

## 2. Parâmetros de Entrada

| Parâmetro              | Descrição                                                                 |
|------------------------|---------------------------------------------------------------------------|
| `Input Polygon Layer`  | Camada vetorial poligonal que define a área de interesse                 |
| `Grid size on x-axis`  | Largura de cada célula (tile) da grade, em unidades do CRS               |
| `Grid size on y-axis`  | Altura de cada célula (tile) da grade, em unidades do CRS                |
| `Related task id`      | (Avançado) ID da atividade relacionada à grade criada                    |
| `Work unit id`         | (Avançado) ID da unidade de trabalho responsável                         |
| `Step id`              | (Avançado) ID da etapa do fluxo de trabalho (ex: validação, revisão)     |
| `Created Review Grid`  | Saída vetorial com os polígonos gerados da grade                         |

### Interface de Parâmetros

Abaixo, temos um exemplo da interface do algoritmo **"Create Review Grid"** no provedor do DSGTools. É nela que o usuário define os valores necessários para a geração da grade.

![Interface Create Review Grid](./assets/modulo-04/img-config-create-review-grid.png)

*Figura 4.3 – Interface do algoritmo "Create Review Grid" com os parâmetros padrão e avançados.*

> ⚠️ **Importante:** Os parâmetros avançados são opcionais, mas úteis para rastreabilidade e controle de etapas do processo.

---

## 3. Parâmetros Avançados

Esses campos são adicionados aos atributos da grade criada. Eles permitem associar cada célula da grade com elementos do processo de produção:

| Campo na grade            | Origem do parâmetro           | Finalidade                                      |
|---------------------------|-------------------------------|------------------------------------------------|
| `atividade_id`            | `Related task id`             | Relaciona a célula com uma tarefa específica   |
| `unidade_trabalho_id`     | `Work unit id`                | Identifica qual equipe ou setor produziu       |
| `etapa_id`                | `Step id`                     | Indica a fase do fluxo (validação, revisão...) |

> **💡 Exemplo prático:** Ao dividir uma área para revisão por diferentes equipes, o ID da equipe e da etapa podem ser registrados automaticamente na grade gerada.

---

## 4. Fluxo Operacional

1. Carregar a camada poligonal no QGIS
2. Abrir o plugin DSGTools e buscar por `Create Review Grid` no provedor de algoritmos
3. Definir os tamanhos da grade em `x` e `y`
4. (Opcional) Preencher os parâmetros avançados: tarefa, unidade e etapa
5. Executar o algoritmo e revisar a grade gerada

---

## 5. Funcionamento

A grade é gerada com base na **extensão da camada poligonal de entrada**, respeitando os espaçamentos definidos nos eixos X e Y.

Depois, a grade é filtrada para manter apenas as células que **intersectam** com a camada original, e cada feição é enriquecida com atributos conforme os parâmetros fornecidos.

> **💡 Dica:** Utilizar um CRS projetado (como UTM) facilita o controle das dimensões da grade.

---

## 6. Saída Esperada

* Uma camada vetorial com feições poligonais regulares
* Atributos adicionais que indicam:
  * ordem (`rank`)
  * se foi visitada (`visited`)
  * IDs de controle (atividade, unidade, etapa)
  * data de atualização (opcionalmente preenchida)

  ![Grade gerada a partir do review](assets/modulo-04/img-result-create-review-grid.png)
*Figura 4.1: Exemplo de grade criada com o Grid Review*

---

## 7. Aplicações Práticas

* Criação de grades para **validação cartográfica**
* Controle de progresso por equipe/setor
* Divisão de áreas para **trabalho colaborativo**
* Geração de relatórios e rastreabilidade em auditorias

---

## 8. Resumo

* Gera grade com base em uma camada existente
* Suporte a atributos de controle (atividade, equipe, etapa)
* Ideal para revisão e segmentação de dados espaciais

> **🔹 Recomendado:** Use um CRS em metros (como UTM) para facilitar a definição das dimensões da grade.

> **⚠️ Atenção:** A camada de entrada deve ser poligonal e conter a área a ser dividida.
