## Algoritmo: Generate Systematic Grid (Gerar Grade Sistemática)

## 1. Introdução

O algoritmo `Generate Systematic Grid` permite a criação de grades sistemáticas baseadas em índices cartográficos (MI/MIR ou INOM), com subdivisões automáticas conforme a escala desejada. É ideal para gerar quadros padronizados usados em mapeamento sistemático do território brasileiro.

> 💡 **Dica:** Muito útil na geração de grades por escala padronizada (ex: 1:250k → 1:50k), com suporte a subdivisões e múltiplos índices de entrada.

---

## 2. Parâmetros de Entrada

| Parâmetro                                 | Descrição                                                                 |
|-------------------------------------------|---------------------------------------------------------------------------|
| `Base scale`                              | Escala de referência do índice de entrada                                |
| `Desired scale`                           | Escala final desejada para subdivisão dos quadros                        |
| `Index type`                              | Tipo de índice usado: `MI/MIR` ou `INOM`                                 |
| `Index`                                   | Código do índice (ex: SB-22-Z-A), permite múltiplos separados por vírgula|
| `CRS`                                     | Sistema de referência de coordenadas de saída                            |
| `Number of subdivisions on x-axis`        | (Avançado) Número de subdivisões no eixo X (horizontal)                  |
| `Number of subdivisions on y-axis`        | (Avançado) Número de subdivisões no eixo Y (vertical)                    |
| `Created Frames`                          | Camada de saída contendo os quadros gerados                              |

> ⚠️ **Importante:** A subdivisão é adaptativa com base na escala final. Parâmetros avançados podem sobrescrever o padrão.

![Configuração Generate Systematic Grid](./assets/modulo-04/img-config-generate-systematic.png)  
*Figura 4.X – Exemplo de saída do algoritimo Generate Systematic Grid.*

---

## 3. Funcionamento

1. O usuário define um ou mais índices cartográficos válidos (ex: `SB-22-Z-A`) e uma escala final desejada.
2. O algoritmo valida cada índice conforme o padrão do tipo selecionado (`MI/MIR` ou `INOM`).
3. A área de cada índice é convertida para a escala desejada, criando subdivisões automáticas.
4. Os quadros resultantes são reprojetados para o CRS escolhido.
5. É possível especificar manualmente o número de subdivisões em X e Y, sobrescrevendo o padrão da escala.

> 💡 **Padrões por escala:**  
> - 1:50k → 2x2  
> - 1:100k → 4x4  
> - 1:250k → 12x8

---

## 4. Fluxo Operacional

1. Abrir o plugin DSGTools e selecionar o algoritmo `Generate Systematic Grid`  
2. Informar a escala base e a escala desejada  
3. Selecionar o tipo de índice e informar um ou mais códigos válidos  
4. Definir o CRS de saída  
5. (Opcional) Definir número de subdivisões manuais  
6. Executar o algoritmo e revisar os quadros gerados  

---

## 5. Atributos da Camada de Saída

| Campo   | Descrição                                   |
|---------|---------------------------------------------|
| `inom`  | Código INOM da feição resultante            |
| `mi`    | Código MI ou MIR correspondente, se houver  |

---

## 6. Saída Esperada

- Camada poligonal com quadros gerados a partir dos índices fornecidos  
- Atributos de rastreabilidade (`mi`, `inom`) preenchidos  
- Compatível com CRS definido e subdivisão por escala  

![Resultado Generate Systematic Grid](./assets/modulo-04/img-result-generate-systematic.png)  
*Figura 4.X – Exemplo de saída do algoritimo Generate Systematic Grid.*

---

## 7. Aplicações Práticas

- Geração de grades para mapeamento sistemático em diversas escalas  
- Planejamento de produção cartográfica orientada por INOM/MI  
- Estruturação de áreas para equipes por subdivisão homogênea  
- Visualização padronizada para mapas topográficos  

---

## 8. Resumo

- Constrói grades padronizadas com base em índices cartográficos válidos  
- Suporte a múltiplos índices, validação automática e subdivisão inteligente  
- Ideal para padronização e planejamento da produção cartográfica brasileira  

> 🔹 **Recomendado:** Para escalas menores, utilize subdivisões maiores para maior controle.  
> ⚠️ **Atenção:** A entrada exige índices válidos e compatíveis com o tipo selecionado (`MI/MIR` ou `INOM`).