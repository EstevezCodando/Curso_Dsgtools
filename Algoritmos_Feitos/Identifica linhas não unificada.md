# Módulo 4: Provedor de Algoritmos - Validação

## Algoritmo: Identificar Linhas Não Unificadas com o Mesmo Conjunto de Atributos

## 1. Introdução

O algoritmo **Identificar Linhas Não Unificadas com o Mesmo Conjunto de Atributos** permite localizar feições lineares que compartilham os mesmos atributos mas que permanecem separadas no plano vetorial, ou seja, que **poderiam ser unidas** por um processo de dissolução, mas não foram.

> 💡 *Dica:* Este processo é útil para validar consistência topológica e de atributos, especialmente em redes como hidrografia, vias ou limites administrativos.

---

## 2. Parâmetros de Entrada

| Parâmetro                    | Descrição                                                                 |
|-----------------------------|---------------------------------------------------------------------------|
| Camada de entrada           | Camada vetorial do tipo linha a ser avaliada                             |
| Processar apenas selecionadas| Se verdadeiro, avalia apenas as feições selecionadas                     |
| Campos a ignorar            | Lista de atributos que devem ser ignorados na comparação de similaridade |
| Ignorar campos virtuais     | Ignora campos calculados dinamicamente no QGIS                           |
| Ignorar campos de chave primária | Ignora identificadores únicos que não devem ser considerados          |
| Camadas de filtro de ponto  | Camadas auxiliares para refinar o processo de identificação              |
| Camadas de filtro de linha  | Camadas auxiliares de linha a serem usadas como contexto de validação    |
| Flags                       | Saída com os pontos onde há separações indevidas                         |

### Interface de Parâmetros

A interface apresenta campos para seleção da camada alvo, campos a ignorar e filtros espaciais:

![Interface do algoritmo](assets/modulo-04/img-config-identificar-linhas-nao-unificadas.png)

*Figura 4.X – Interface do algoritmo "Identificar Linhas Não Unificadas com o Mesmo Conjunto de Atributos".*

> ⚠️ *Atenção:* O algoritmo **requer a biblioteca `networkx`** instalada no ambiente Python do QGIS.

---

## 3. Fluxo Operacional

1. Acessar o algoritmo via provedor DSGTools no QGIS
2. Selecionar a camada de linhas a ser analisada
3. (Opcional) Marcar para considerar apenas feições selecionadas
4. (Opcional) Indicar campos a ignorar na comparação
5. Executar o algoritmo
6. Verificar os pontos sinalizados como locais onde linhas poderiam estar unidas

---

## 4. Funcionamento

O algoritmo executa as seguintes etapas:

1. Cria uma cache local da camada de entrada;
2. Gera nós nos vértices inicial e final das linhas;
3. Constrói uma estrutura de grafo com a biblioteca `networkx`;
4. Compara atributos das linhas ignorando os campos definidos;
5. Identifica arestas que compartilham nós e atributos, mas que estão separadas;
6. Sinaliza esses pontos com *flags* do tipo ponto para posterior inspeção.

> 💡 *Dica:* Utilize camadas auxiliares de filtro para refinar a detecção, excluindo pontos de separação justificados.

---

## 5. Saída Esperada

- Uma **camada do tipo ponto**, com os locais onde duas ou mais linhas com mesmos atributos poderiam estar unidas.
- Atributos contendo informações descritivas da inconsistência.
- Essa saída pode ser inspecionada e tratada manualmente ou servir de base para dissoluções automáticas.

---

## 6. Aplicações Práticas

- Validação de feições de rede (rios, ruas, dutos)
- Verificação de integridade topológica em limites administrativos
- Preparação de dados para processos de dissolução e generalização
- Identificação de erros de digitalização com duplicidade desnecessária

---

## 7. Resumo

- Algoritmo de verificação de separações indevidas entre linhas
- Compara atributos ignorando campos definidos
- Requer `networkx` para construção de grafos
- Gera pontos sinalizando locais de possível unificação
- Útil para topologia, qualidade de dados e pré-processamento

> 🔹 *Recomendado:* Utilize este algoritmo antes de realizar dissoluções por atributos para garantir que os dados estejam coesos.

> ⚠️ *Atenção:* Linhas separadas por intenção (como mudança de geometria) devem ser filtradas previamente com camadas auxiliares de contexto.
