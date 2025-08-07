# Módulo 4: Provedor de Algoritmos - Processamento de Linhas

## Algoritmo: Estender Linhas até os Limites Geográficos

## 1. Introdução

O algoritmo **Estender Linhas até os Limites Geográficos** tem como objetivo prolongar os segmentos iniciais e finais de linhas de uma camada vetorial, até que essas geometrias interceptem uma camada de limite geográfico definida pelo usuário. Essa extensão respeita um valor de tolerância informado, delimitando a distância máxima de prolongamento.

> 💡 *Dica:* Este algoritmo é útil para estender redes lineares (como hidrografia ou rodovias) até os limites administrativos ou de folha cartográfica.

---

## 2. Parâmetros de Entrada

| Parâmetro                      | Descrição                                                                 |
|-------------------------------|---------------------------------------------------------------------------|
| Camada de entrada             | Camada vetorial com feições lineares a serem estendidas                   |
| Processar apenas selecionadas | Se ativado, o algoritmo trabalhará apenas com as feições selecionadas     |
| Limites geográficos           | Camada poligonal que representa o limite até onde as linhas devem alcançar|
| Comprimento de extensão       | Distância máxima (tolerância) para prolongar as linhas                    |

### Interface de Parâmetros

Abaixo está um exemplo da interface do algoritmo *Estender Linhas até os Limites Geográficos* no QGIS:

![Interface de parâmetros do algoritmo](./assets/modulo-04/img-param-estender-linhas-limite.png)
*Figura 4.X – Interface do algoritmo com os parâmetros principais*

> ⚠️ *Atenção:* Certifique-se de que a camada de limites esteja em formato poligonal e que possua geometria válida.

---

## 3. Fluxo Operacional

1. Abrir o QGIS e carregar o plugin DSGTools
2. Acessar o algoritmo pelo provedor DSGTools (atalho: `extendlinestogeographicbounds`)
3. Selecionar a camada linear a ser estendida
4. Informar a camada de limites geográficos
5. Definir o valor do comprimento de extensão (em unidades da camada)
6. Executar o algoritmo e revisar os resultados

---

## 4. Funcionamento

O algoritmo realiza as seguintes etapas internas:

1. **Unificação** das geometrias de entrada (com ou sem seleção);
2. **Extração das linhas de contorno** da camada de limites geográficos;
3. **Criação de um buffer** ao redor dessas linhas de contorno, com a tolerância informada;
4. **Verificação de interseção** entre os vértices de início/fim das linhas e o buffer criado;
5. **Extensão das linhas** cujos vértices se encontram dentro da área do buffer;
6. **Atualização da camada original** com as novas geometrias estendidas.

> 💡 *Dica:* O algoritmo ignora geometrias fechadas (anéis) durante a extensão, para preservar a topologia.

---

## 5. Saída Esperada

* As geometrias da camada original são atualizadas com novas extensões nas extremidades, quando aplicável.
* As alterações respeitam a tolerância fornecida, mantendo a coerência com os limites geográficos.

![Exemplo de linhas estendidas até os limites](./assets/modulo-04/img-linhas-estendidas-exemplo.png)
*Figura 4.X – Linhas antes e depois do processo de extensão*

---

## 6. Aplicações Práticas

* Extensão de redes de drenagem até os limites de folha
* Ajuste de eixos de vias até bordas de área de interesse
* Regularização de redes para integração em bases contínuas

---

## 7. Resumo

* Algoritmo de atualização e extensão de geometrias lineares
* Trabalha com limites definidos pelo usuário
* Evita sobreposição indesejada, controlando via buffer/tolerância
* Preserva geometrias fechadas
* Compatível com workflows de controle de qualidade espacial

> 🔹 *Recomendado:* Trabalhar com camadas em sistema de coordenadas projetado (como UTM), para facilitar o controle da extensão em metros.

---