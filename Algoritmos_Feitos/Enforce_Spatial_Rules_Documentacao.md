# Módulo 4: Provedor de Algoritmos - QA Tools: Object Proximity and Relationships

## Algoritmo: Enforce Spatial Rules (Aplicar regras espaciais)

## 1. Introdução

O algoritmo `Enforce Spatial Rules` aplica um conjunto de **regras espaciais** definidas pelo usuário para verificar a **consistência topológica** e **relacional** entre camadas vetoriais. Ele é ideal para validar se objetos seguem relações obrigatórias, como contato, interseção ou distância mínima entre feições.

> 💡 **Dica:** Essencial para controle de qualidade em bancos de dados geográficos estruturados e integrados.

---

## 2. Parâmetros de Entrada

| Parâmetro            | Descrição                                                                 |
|----------------------|---------------------------------------------------------------------------|
| `Spatial rules set`  | Conjunto de regras espaciais definidas pelo usuário                      |
| `Point flags`        | Camada de saída com flags do tipo ponto, para violações em geometrias pontuais |
| `Linestring flags`   | Camada de saída com flags do tipo linha, para violações em geometrias lineares |
| `Polygon flags`      | Camada de saída com flags do tipo polígono, para violações em geometrias poligonais |

> ⚠️ **Observação:** As regras espaciais devem ser válidas e aplicáveis a camadas carregadas no projeto.

---

## 3. Fluxo Operacional

1. O usuário define um **conjunto de regras espaciais** (ex: “feições de tipo A devem tocar feições de tipo B”)  
2. Cada regra é verificada por meio de testes espaciais entre as camadas envolvidas  
3. Quando uma regra é violada, a geometria correspondente é registrada na camada de flags apropriada (ponto, linha ou polígono)  
4. Cada flag inclui uma descrição textual da violação  

---

## 4. Funcionamento

As regras são instanciadas como objetos `SpatialRule`, processadas por `SpatialRelationsHandler`, que testa sistematicamente cada condição.  
As violações são agrupadas por tipo de geometria e registradas em camadas de saída distintas com atributos explicativos.

---

## 5. Saída Esperada

- Três camadas vetoriais (ponto, linha, polígono) com as geometrias que violam as regras  
- Cada feição contém uma descrição no campo `reason`, como:  
  `"Rule 'must touch river' broken: object is too far from river layer"`

---

## 6. Aplicações Práticas

- Validação de modelos de dados geográficos (ex: feições de uso da terra, drenagem, edificações)  
- Garantia de regras obrigatórias entre classes de objetos (ex: contato entre via e quadra)  
- Apoio a bancos de dados espaciais com integridade topológica  
- Detecção automatizada de erros relacionais entre feições em diferentes camadas  

---

## 7. Resumo

- Executa regras espaciais sobre múltiplas camadas  
- Detecta violações e gera flags separados por tipo geométrico  
- Garante integridade e relacionamento espacial entre feições  

> 🔹 **Recomendado:** Combine com algoritmos de correção para ajustar as violações automaticamente.  
> ⚠️ **Atenção:** As regras devem estar corretamente configuradas e as camadas envolvidas precisam estar carregadas no projeto.