# Guidelines e Estrutura - Curso EAD DSGTools

## 1. Guidelines de Padronização

### 1.1 Padrão de Nome de Arquivo
- **Formato:** `modulo-XX-nome-descritivo.md`
- **Exemplos:**
  - `modulo-01-introducao-dsgtools.md`
  - `modulo-02-inde-infraestrutura-dados.md`
  - `modulo-03-extracao-geoinformacao.md`
- **Arquivos auxiliares:** `modulo-XX-exercicios.md`, `modulo-XX-referencias.md`
- **Imagens:** `assets/modulo-XX/img-nome-descritivo.png`

### 1.2 Estilo de Escrita
- **Tom:** Técnico, mas didático e acessível
- **Pessoa:** Terceira pessoa do singular ou infinitivo impessoal
- **Tempos verbais:** Presente do indicativo para conceitos, imperativo para instruções
- **Siglas:** Sempre explicar na primeira ocorrência: "Sistema de Informação Geográfica (SIG)"
- **Termos técnicos:** Definir claramente quando introduzidos pela primeira vez

### 1.3 Formatação de Escrita
```markdown
# Título Principal (H1) - Apenas um por arquivo
## Seções Principais (H2)
### Subseções (H3)
#### Detalhamento (H4) - máximo recomendado

**Negrito:** Para destacar conceitos importantes
*Itálico:* Para termos em outros idiomas ou ênfase
`Código inline:` Para nomes de ferramentas, botões, menus
```

### 1.4 Especificações Técnicas
- **Versões de software:** Sempre especificar versões utilizadas
- **Requisitos mínimos:** Listar no início de cada módulo quando aplicável
- **Configurações:** Detalhar configurações específicas necessárias
- **Paths e diretórios:** Usar notação universal (`/` para separadores)

### 1.5 Convenções de Captura de Tela
- **Resolução:** 1920x1080 ou superior
- **Formato:** PNG para capturas com texto, JPG para fotografias
- **Compressão:** Otimizar para web (máximo 500KB por imagem)
- **Foco:** Destacar área relevante com bordas vermelhas quando necessário
- **Anonimização:** Remover informações pessoais ou sensíveis

### 1.6 Referência de Imagens no Markdown
```markdown
![Descrição alternativa da imagem](assets/modulo-01/img-instalacao-qgis.png)
*Figura 1.1: Tela de instalação do QGIS 3.34 LTR*
```

### 1.7 Tratamento de Imagens
- **Nomenclatura:** `img-contexto-acao.png`
- **Numeração:** Sequencial por módulo
- **Redimensionamento:** Máximo 800px de largura para capturas de tela
- **Anotações:** Usar caixas vermelhas, setas e numeração quando necessário

### 1.8 Estrutura de Conteúdo por Módulo
1. **Introdução/Objetivos**
2. **Pré-requisitos**
3. **Conteúdo principal** (dividido em seções lógicas)
4. **Resumo/Pontos-chave**
5. **Material complementar**

### 1.9 Estilo de Organização
- **Blocos de código:** Usar syntax highlighting apropriado
- **Listas:** Usar `-` para listas não numeradas, `1.` para numeradas
- **Tabelas:** Para comparações e especificações técnicas
- **Callouts:** Para alertas, dicas e avisos importantes

```markdown
> **💡 Dica:** Informações úteis para facilitar o aprendizado
> 
> **⚠️ Atenção:** Alertas sobre possíveis problemas
> 
> **📋 Pré-requisito:** Conhecimentos ou configurações necessárias
```

## 2. Estrutura de Arquivos

```
curso-dsgtools-ead/
├── README.md
├── CONTRIBUTING.md
├── assets/
│   ├── modulo-01/
│   │   ├── img-visao-geral-curso.png
│   │   ├── img-instalacao-qgis.png
│   │   └── img-componentes-dsgtools.png
│   ├── modulo-02/
│   ├── modulo-03/
│   ├── modulo-04/
│   ├── modulo-05/
│   └── comum/
│       ├── logo-dsgtools.png
│       └── template-conteudo.png
├── modulos/
│   ├── modulo-01-introducao-dsgtools.md
│   ├── modulo-02-inde-infraestrutura-dados.md
│   ├── modulo-03-extracao-geoinformacao.md
│   ├── modulo-04-provedor-algoritmos.md
│   └── modulo-05-controle-qualidade.md
├── referencias/
│   ├── bibliografia.md
│   ├── glossario.md
│   └── links-uteis.md
└── templates/
    └── template-modulo.md
```

## 3. Estrutura de Tópicos por Módulo

### Módulo 1: Introdução ao DSGTools
1. **Visão Geral do Curso**
2. **Defesa e Segurança Geoespacial (DSG)**
3. **Histórico do Desenvolvimento do DSGTools**
4. **Conceitos de Geoinformação**
5. **QGIS - Instalação e Configuração**
6. **DSGTools - Instalação e Configuração**
7. **Componentes do DSGTools**

### Módulo 2: INDE e Infraestrutura de Dados
1. **Infraestrutura Nacional de Dados Espaciais (INDE)**
2. **Especificações Técnicas e Normas**
3. **Criação de Bancos de Dados Geoespaciais**
4. **Carregamento e Estruturação de Camadas**
5. **Domínios Resolvidos**
6. **Conexão e Consumo de Dados Oficiais**

### Módulo 3: Extração de Geoinformação
1. **Ferramentas de Digitalização Avançadas**
2. **Controle de Visualização e Seleção**
3. **Menu de Aquisição de Dados**
4. **Processo de Revisão e Controle**
5. **Processamento de Dados Raster**

### Módulo 4: Provedor de Algoritmos
1. **Algoritmos de Inventário**
2. **Algoritmos de Grade (Grid)**
3. **Algoritmos Geométricos**
4. **Processamento de Linhas e Redes**
5. **Algoritmos de Validação**
6. **Manipulação de Vértices**
7. **Processos de Ajuste (Snap)**
8. **Generalização e Regras Espaciais**
9. **Processamento de Terreno**

### Módulo 5: Controle de Qualidade
1. **Introdução ao Workflow Toolbox**
2. **Construção de Modelos**
3. **Desenvolvimento de Workflows**
4. **Execução e Monitoramento**
5. **Tratamento de Resultados e Exceções**

## 4. Esqueletos dos Arquivos

### Template Base para Módulos
```markdown
# Módulo X: [Nome do Módulo]

## Objetivos de Aprendizagem
- [ ] Objetivo 1
- [ ] Objetivo 2
- [ ] Objetivo 3

## Pré-requisitos
> **📋 Pré-requisito:** Liste aqui os conhecimentos necessários

## Introdução
Contextualize o módulo e sua importância...

## [Seção Principal 1]
### [Subseção 1.1]
Conteúdo detalhado...

![Descrição da imagem](assets/modulo-X/img-exemplo.png)
*Figura X.1: Descrição da figura*

### [Subseção 1.2]
Conteúdo detalhado...

## [Seção Principal 2]
### [Subseção 2.1]
Conteúdo detalhado...

## Resumo
- Ponto-chave 1
- Ponto-chave 2
- Ponto-chave 3

## Material Complementar
- [Link para documentação oficial](https://exemplo.com)
- [Vídeo tutorial](https://exemplo.com)

## Próximo Módulo
Preparação para o [Módulo X+1: Nome do Próximo Módulo](modulo-X+1-nome.md)
```

Esta estrutura garante consistência, facilita a manutenção e proporciona um conteúdo organizado e profissional.