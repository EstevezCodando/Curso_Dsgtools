# Esqueletos dos Módulos - Curso DSGTools

## modulo-01-introducao-dsgtools.md

```markdown
# Módulo 1: Introdução ao Curso

**Instrutor:** Cap Borba

## Objetivos de Aprendizagem
- [ ] Compreender a visão geral e objetivos do curso
- [ ] Conhecer os conceitos de DSG
- [ ] Compreender o histórico do desenvolvimento do DSGTools
- [ ] Entender os conceitos de geoinformação
- [ ] Conhecer o QGIS e sua instalação
- [ ] Instalar o DSGTools
- [ ] Conhecer os componentes do DSGTools

## Pré-requisitos
> **📋 Pré-requisito:** Conhecimentos básicos de informática e conceitos geográficos

## 1. Visão Geral do Curso

### 1.1 Objetivos do Curso
### 1.2 Metodologia e Estrutura
### 1.3 Público-alvo
### 1.4 Carga Horária e Cronograma

## 2. DSG

### 2.1 Breve Histórico
### 2.2 Estrutura e Subordinação


## 3. Histórico do Desenvolvimento do DSGTools

## 4. Geoinformação

### 4.1 Definições Básicas
### 4.2 Sistemas de Informação Geográfica
### 4.3 Dados Geoespaciais
### 4.4 Metadados Geográficos

## 5. QGIS

### 5.1 Instalação (escolher versão LTR do QGIS)
#### 5.1.1 Por que usar versão LTR
#### 5.1.2 Download e Instalação
#### 5.1.3 Configurações Iniciais
#### 5.1.4 Verificação da Instalação

## 6. Instalação do DSGTools

### 6.1 Pré-requisitos do Sistema
### 6.2 Instalação via Repositório Oficial
### 6.3 Configurações Pós-instalação
### 6.4 Verificação da Instalação

## 7. Apresentação das Componentes do DSGTools

### 7.1 Visão Geral da Interface
### 7.2 Barras de Ferramentas
### 7.3 Painéis e Docks
### 7.4 Menus Principais
### 7.5 Fluxo de Trabalho Básico

## Resumo
- O DSGTools é uma suíte abrangente para trabalho com dados geoespaciais militares
- A instalação correta do QGIS LTR é fundamental para o funcionamento
- Os componentes se integram para formar um ambiente completo de trabalho

## Material Complementar
- [Documentação oficial do DSGTools](https://github.com/dsgoficial/DsgTools)
- [Manual do usuário QGIS](https://docs.qgis.org)

## Próximo Módulo
Preparação para o [Módulo 2: INDE e Infraestrutura de Dados](modulo-02-inde-infraestrutura-dados.md)
```

---

## modulo-02-inde-infraestrutura-dados.md

```markdown
# Módulo 2: INDE e Infraestrutura de Dados

**Instrutor:** 1º Ten Campos

## Objetivos de Aprendizagem
- [ ] Compreender a INDE e normas relacionadas
- [ ] Conhecer as especificações técnicas (ET-EDGV, ET-ADGV, ET-RDG, ET-CQDG)
- [ ] Criar bancos de dados PostGIS e SpatiaLite
- [ ] Realizar carregamento de camadas
- [ ] Trabalhar com domínios resolvidos (consultas e montar labels)
- [ ] Conectar e consumir dados oficiais via DSGTools

## Pré-requisitos
> **📋 Pré-requisito:** Módulo 1 concluído, conhecimentos básicos de banco de dados

## 1. INDE e Normas

### 1.1 Infraestrutura Nacional de Dados Espaciais (INDE)
### 1.2 ET-EDGV (Especificação Técnica para Estruturação de Dados Geoespaciais Vetoriais)
### 1.3 ET-ADGV (Especificação Técnica para Aquisição de Dados Geoespaciais Vetoriais)
### 1.4 ET-RDG (Especificação Técnica para Representação de Dados Geoespaciais)
### 1.5 ET-CQDG (Especificação Técnica para Controle de Qualidade de Dados Geoespaciais)

## 2. Criação de Bancos de Dados

### 2.1 PostGIS

### 2.2 SpatiaLite

## 3. Carregamento de Camadas

## 4. Domínios Resolvidos

## 5. Conexão e Consumo de Dados Oficiais

### 5.1 Consumo dos Serviços via DSGTools
### 5.2 Configuração de Conexões
### 5.3 Consumo de Dados via WMS/WFS
### 5.4 Sincronização e Atualização
### 5.5 Boas Práticas de Consumo

## Resumo
- A INDE padroniza a estruturação de dados geoespaciais no Brasil
- PostGIS oferece maior robustez, SpatiaLite maior portabilidade
- Domínios resolvidos facilitam a entrada e consistência dos dados
- Conexão com dados oficiais amplia as possibilidades de análise

## Material Complementar
- [Portal da INDE](https://www.inde.gov.br)
- [Especificações Técnicas Oficiais](https://www.geoportal.eb.mil.br)

## Próximo Módulo
Preparação para o [Módulo 3: Extração de Geoinformação](modulo-03-extracao-geoinformacao.md)
```

---

## modulo-03-extracao-geoinformacao.md

```markdown
# Módulo 3: Extração de Geoinformação

**Instrutor:** 1º Ten Luiz Guilherme

## Objetivos de Aprendizagem
- [ ] Dominar as ferramentas de digitalização do DSGTools
- [ ] Utilizar controles de visualização e seleção
- [ ] Aplicar o menu de aquisição
- [ ] Executar o processo de revisão
- [ ] Trabalhar com a barra de raster

## Pré-requisitos
> **📋 Pré-requisito:** Módulos 1 e 2 concluídos, conhecimento básico de digitalização

## 1. Ferramentas de Digitalização do DSGTools

### 1.1 Seletor Genérico
### 1.2 Ângulo Reto
### 1.3 Free Hand
### 1.4 Flip
### 1.5 Trim-Extend
### 1.6 Measure While Digitizing
### 1.7 Iterador de Feições
### 1.8 Ferramenta de Área Mínima
### 1.9 Linha Cotadora
### 1.10 Medir Enquanto Digitaliza

## 2. Controles de Interface

### 2.1 Ligar e Desligar Rótulos
### 2.2 Ligar e Desligar Visibilidade da Camada Ativa
### 2.3 Salvar Selecionadas como Memory Layer
### 2.4 Filtrar Camada

## 3. Menu de Aquisição

### 3.1 Estrutura do Menu
### 3.2 Configuração de Templates
### 3.3 Aquisição por Categoria
### 3.4 Fluxos de Trabalho

## 4. Ferramenta de Revisão

### 4.1 Processo de Revisão
#### 4.1.1 Configuração do Processo (processing)

### 4.2 Barra de Ferramentas de Revisão
#### 4.2.1 Ferramentas Disponíveis
#### 4.2.2 Configuração
#### 4.2.3 Uso

## 5. Barra de Raster

### 5.1 Ferramentas da Barra de Raster
### 5.2 Integração com Dados Vetoriais
### 5.3 Análises Raster-Vetor
### 5.4 Processamento de Imagens

## Resumo
- As ferramentas de digitalização do DSGTools otimizam o processo de captura
- Os controles de interface melhoram a produtividade
- O processo de revisão garante a qualidade dos dados
- A barra de raster permite análises integradas

## Material Complementar
- [Guia de Digitalização](https://exemplo.com)
- [Manual de Revisão](https://exemplo.com)

## Próximo Módulo
Preparação para o [Módulo 4: Provedor de Algoritmos](modulo-04-provedor-algoritmos.md)
```

---

## modulo-04-provedor-algoritmos.md

```markdown
# Módulo 4: Provedor de Algoritmos

**Instrutores:** 2º Sgt Alvarez / 3º Sgt Godinho

## Objetivos de Aprendizagem
- [ ] Compreender e utilizar algoritmos de inventário
- [ ] Aplicar todos os algoritmos de grid
- [ ] Executar algoritmos geométricos específicos
- [ ] Implementar algoritmos de validação
- [ ] Realizar processamento de vértices e snap
- [ ] Aplicar algoritmos de terreno

## Pré-requisitos
> **📋 Pré-requisito:** Módulos 1, 2 e 3 concluídos, conhecimento intermediário de SIG

## 1. Inventário

### 1.1 Conceitos e Aplicações
### 1.2 Configuração de Parâmetros
### 1.3 Interpretação de Resultados

## 2. Grid Algorithms (Todos)

### 2.1 Tipos de Grade Disponíveis
### 2.2 Configuração de Parâmetros
### 2.3 Aplicações Práticas
### 2.4 Otimização de Performance

## 3. Geometric Algorithms

### 3.1 Deaggregate
### 3.2 Donut Hole Extractor
### 3.3 Extract by DE9IM
### 3.4 Line on Area Overlayer
### 3.5 Line on Line Overlayer
### 3.6 Polygon Tiler
### 3.7 Split Lines at Maximum Length

## 4. Processamento de Linhas

### 4.1 Identify Unmerged Lines
### 4.2 Merge Lines with Same Attribute Set
### 4.3 Extend Lines to Geographic Boundary
### 4.4 Generalização de Drenagem (Generalize Network Edges With Length Algorithm)

## 5. Algoritmos de Validação

### 5.1 Geometria Inválida
### 5.2 Identificar Elementos Pequenos
### 5.3 Identificar Ângulos Pequenos
### 5.4 Identificar Geometrias Duplicadas / Feições Duplicadas
### 5.5 Identificar Gaps
### 5.6 Identificar Overlaps
### 5.7 Dangles

## 6. Vertex Handling

### 6.1 Identificar Vértices Duplicados
### 6.2 Identify Vertex Near Edges
### 6.3 Identify Unshared Vertex on Intersections
### 6.4 Identify Unshared Vertex on Shared Edges

## 7. Snap Processes

### 7.1 Clean
### 7.2 Snap Hierárquico
### 7.3 Anchored Snapper

## 8. Douglas Peucker Topológico

### 8.1 Algoritmo e Aplicação
### 8.2 Configuração de Tolerâncias
### 8.3 Preservação Topológica

## 9. Enforce Spatial Rules

### 9.1 Definição de Regras
### 9.2 Implementação
### 9.3 Validação de Conformidade

## 10. Terrain Processes (Exceto Ponto Cotado)

### 10.1 Algoritmos Disponíveis
### 10.2 Configuração de Parâmetros
### 10.3 Integração com Outros Processos

> **⚠️ Atenção:** Algoritmos de ponto cotado não são abordados neste módulo

## Resumo
- Os algoritmos do DSGTools cobrem todas as etapas do processamento geoespacial
- A validação automática é fundamental para garantir qualidade
- Processos de snap e limpeza otimizam a topologia dos dados
- A combinação de algoritmos permite workflows eficientes

## Material Complementar
- [Documentação dos Algoritmos](https://exemplo.com)
- [Casos de Uso](https://exemplo.com)

## Próximo Módulo
Preparação para o [Módulo 5: Controle de Qualidade](modulo-05-controle-qualidade.md)
```

---

## modulo-05-controle-qualidade.md

```markdown
# Módulo 5: Controle de Qualidade

**Instrutor:** 3º Sgt Gustavo Pereira

## Objetivos de Aprendizagem
- [ ] Compreender o Workflow Toolbox
- [ ] Construir modelos usando o model helper
- [ ] Compreender especificidades dos modelos
- [ ] Montar workflows completos
- [ ] Executar workflows existentes
- [ ] Trabalhar com modalidades de tratamento

## Pré-requisitos
> **📋 Pré-requisito:** Todos os módulos anteriores concluídos

## 1. Workflow Toolbox

### 1.1 Conceitos Fundamentais
### 1.2 Arquitetura do Sistema
### 1.3 Interface do Usuário
### 1.4 Integração com QGIS Processing

## 2. Como Montar os Models

### 2.1 Model Helper
#### 2.1.1 Funcionalidades do Model Helper
#### 2.1.2 Assistente de Criação
#### 2.1.3 Templates e Configurações

### 2.2 Especificidades dos Modelos

## 3. Como Montar o Workflow

## 4. Executar um Workflow Existente

## 5. Modalidades de Tratamento

### 5.1 Falso Positivo

### 5.2 Voltar Etapa

### 5.3 Salvar no Projeto

### 5.4 Outras Modalidades

## Resumo
- O Workflow Toolbox automatiza processos de controle de qualidade
- A construção de modelos permite customização para necessidades específicas
- O monitoramento garante execução confiável
- As modalidades de tratamento oferecem flexibilidade no processo

## Material Complementar
- [Guia do Workflow Toolbox](https://exemplo.com)
- [Biblioteca de Modelos](https://exemplo.com)

```

Esta estrutura garante fidelidade à ementa original, facilita a colaboração entre instrutores e proporciona conteúdo organizado e profissional para o curso EAD de DSGTools.