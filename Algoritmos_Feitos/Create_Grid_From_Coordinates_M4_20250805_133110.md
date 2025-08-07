
# Módulo 4: Provedor de Algoritmos - Grid

## Algoritmo: Create Grid From Coordinates (Criar Grade a partir de Coordenadas)

## 1. Introdução

O algoritmo `Create Grid From Coordinates` permite a geração de uma grade regular com base em coordenadas geográficas fornecidas pelo usuário. É ideal para subdividir áreas retangulares em blocos menores de forma padronizada.

> **💡 Dica:** Esse processo é especialmente útil em contextos de planejamento cartográfico e organização espacial de dados.

---

## 2. Parâmetros de Entrada

| Parâmetro                     | Descrição                                               |
| -----------------------------|---------------------------------------------------------|
| `Min x coordinates`           | Coordenada X mínima do canto inferior esquerdo da grade |
| `Min y coordinates`           | Coordenada Y mínima do canto inferior esquerdo da grade |
| `Max x coordinates`           | Coordenada X máxima do canto superior direito da grade  |
| `Max y coordinates`           | Coordenada Y máxima do canto superior direito da grade  |
| `Number of subdivisions on x` | Quantidade de colunas (tiles) ao longo do eixo X        |
| `Number of subdivisions on y` | Quantidade de linhas (tiles) ao longo do eixo Y         |
| `CRS`                         | Sistema de Referência de Coordenadas da grade           |
| `Grid`                        | Saída vetorial com feições poligonais                   |

### Interface de Parâmetros

Abaixo, temos um exemplo da interface do algoritmo **"Create Grid From Coordinates"** no provedor do DSGTools. É nela que o usuário define os valores necessários para a geração da grade regular.

![Interface de Parâmetros](./assets/modulo-04/img-config-create-grid-coordenadas.png)

*Figura 4.2 – Interface do algoritmo "Create Grid From Coordinates" com os parâmetros a serem preenchidos.*

> ⚠️ **Atenção:** Certifique-se de que:
>
> - Os valores de `Min` e `Max` são coerentes (a diferença deve ser maior que zero).
> - O `CRS` está corretamente definido (não pode estar como `invalid projection`).
> - As subdivisões nos eixos `x` e `y` devem ser números inteiros positivos.

---

## 3. Fluxo Operacional

1. Abrir o QGIS e carregar o plugin DSGTools  
2. Acessar o algoritmo no provedor de algoritmos e procurar pelo nome do algoritimo `(Atalho : creategridfromcoordinatesalgorithm)`  
3. Preencher as coordenadas mínimas e máximas  
4. Definir `Delta X` e `Delta Y` conforme a escala desejada  
5. Executar o algoritmo e visualizar a camada gerada  

---

## 4. Funcionamento

O algoritmo utiliza as coordenadas mínimas e máximas fornecidas, juntamente com o número de subdivisões nos eixos X e Y, para calcular o tamanho de cada célula da grade. Em seguida, gera uma malha composta por polígonos regulares.

> **💡 Dica:** Utilizar um sistema de coordenadas projetado (como UTM) facilita a interpretação do espaçamento entre células.

---

## 5. Saída Esperada

* Uma camada vetorial contendo polígonos regulares.
* Geometrias válidas e compatíveis com operações de análise espacial, como interseção, seleção e recorte.

![Grade gerada a partir de coordenadas](assets/modulo-04/img-result-create-grid-coordenadas.png)  
*Figura 4.1: Exemplo de grade regular criada com base em coordenadas e subdivisões definidas*

---

## 6. Aplicações Práticas

* Indexação de dados em grandes áreas  
* Planejamento de coleta de campo  
* Divisão espacial para processamento  
* Segmentação para aquisição de dados  
* Geração de folhas cartográficas no Compositor de Impressão do QGIS  

---

## 7. Resumo

* Algoritmo para criação de grades regulares  
* Interface intuitiva com controle total da malha gerada  
* Adequado para diferentes contextos de análise espacial em SIG  

> **🔹 Recomendado:** Utilize coordenadas em metros para facilitar o cálculo de dimensões.  
> **⚠️ Atenção:** Verifique se o sistema de referência (CRS) está compatível com os dados e com os objetivos do projeto.
