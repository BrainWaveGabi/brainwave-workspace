---
name: planejar-diler
description: >
  Planeja o calendário mensal de conteúdo do Dr. Diler.
  Analisa dados do mês anterior, pesquisa referências com embasamento científico,
  gera copy completa para aprovação e só cria o card no Notion após confirmação.
  Diretrizes do CFM aplicadas automaticamente.
  Use: "vamos planejar o mês do Diler", "montar o calendário do Diler", /planejar-diler.
---

# /planejar-diler — Planejamento Mensal de Conteúdo

## Cliente
**Pasta:** `clientes/dr-diler/`
**Conselho:** CFM — Resolução 2336/2023
**Estrutura no Notion:** linhas editoriais

## Dependências
- `clientes/dr-diler/CLIENTE.md` — linhas editoriais, mix semanal, tom de voz
- `clientes/dr-diler/conhecimento/` — transcrições, lives, entrevistas, referências
- `_contexto/preferencias.md` — regras gerais de escrita
- `.claude/skills/planejar-conteudo/diretrizes-conselhos.md` — diretrizes do CFM

---

## Workflow

### Fase 0 — Análise do mês anterior

Perguntar: "Tem dados de performance do mês passado pra analisar antes de planejar?"

Se sim, pedir o relatório ou acessar via Notion MCP. Identificar:
- Formatos com maior alcance e engajamento
- Temas que mais performaram
- O que não funcionou

Apresentar resumo curto e considerar na distribuição do mês. Se não tiver dados, seguir sem essa etapa.

---

### Fase 1 — Carregar contexto

Ler `clientes/dr-diler/CLIENTE.md` e extrair:
- Linhas editoriais com pesos e frequências
- Mix semanal (quantos por semana, por linha)
- Formatos ativos e canais

Ler materiais em `clientes/dr-diler/conhecimento/` para calibrar linguagem e repertório do Dr. Diler.

Carregar diretrizes do CFM em `.claude/skills/planejar-conteudo/diretrizes-conselhos.md`.

---

### Fase 2 — Referências e pesquisa

Perguntar: "Quais referências você tem pra esse mês? Links, temas, transcrições ou quer pesquisar."

- **YouTube** → extrair transcrição: `yt-dlp --write-auto-sub --skip-download --sub-format vtt "[URL]"`
- **Link de post/artigo** → ler via WebFetch
- **Roteiro ou texto de base** → usar como estrutura e adaptar ao cliente
- **Tema livre** → gerar com base no CLIENTE.md
- **Pedido de pesquisa** → WebSearch com termos do tema

**Embasamento científico obrigatório:** para todo conteúdo médico, localizar referência científica antes de escrever. O estudo deve:
- Ter DOI
- Publicado nos últimos 3 anos
- Em canal reconhecido: PubMed, MedScape, ResearchGate, Harvard Medical Review, New England Journal of Medicine, The Lancet ou equivalente

Usar WebSearch/WebFetch para confirmar a referência antes de usar.

---

### Fase 3 — Plano do mês

Propor a distribuição de peças respeitando o mix de linhas editoriais do Dr. Diler:

> "Para o Dr. Diler em [mês]:
> Semana 1: [peça — linha editorial — formato] ...
> Começo pela semana 1?"

Aguardar confirmação antes de gerar qualquer copy.

---

### Fase 4 — Copy + aprovação + Notion

Para cada conteúdo, gerar e apresentar para aprovação:

---
**CONTEÚDO [número]**
**Formato:** [Carrossel / Reels / Card único / YouTube / Stories]
**Linha editorial:** [nome]
**Funil:** [Topo / Meio / Fundo / Topo-meio]
**Data prevista:** [semana X]

**Hook:**
[gancho que funciona na fala E na legenda ao mesmo tempo]

**Desenvolvimento:**
[carrossel: slide a slide | vídeo: roteiro por blocos com marcação de tempo | card: texto único]

**Legenda:**
[aprofunda o conteúdo — não resume nem repete]
Este conteúdo é apenas informativo e não substitui a consulta médica.

#hashtag1 #hashtag2 #hashtag3 #hashtag4 #hashtag5

**Referência científica:**
[Autor, Título, Revista, Ano. DOI: xxx]

**Referência visual:** [estilo ou referência sugerida]
**Instruções de design/edição:** [orientações específicas se necessário]

---

Perguntar: "Aprovado pra criar no Notion ou quer ajustar?"

Só criar o card no Notion após confirmação explícita. Ao criar, preencher todas as propriedades: Título, Formato, Canais, Tipo de conteúdo, Funil, Data de Publicação, Cliente.

---

### Fase 5 — Checagem CFM

Antes de apresentar cada peça:
- Promessa de resultado? → reescrever
- Superlativo ou comparação? → reescrever
- Afirmação médica sem referência? → buscar antes de entregar
- Usando "consulta" (não "avaliação gratuita")? → corrigir se necessário

---

## Regras

- Ler `clientes/dr-diler/conhecimento/` antes de escrever
- Tom de voz segue o Dr. Diler, não a BrainWave
- Hook funciona com e sem som
- Legenda aprofunda — nunca resume
- 5 hashtags em todas as legendas
- Disclaimer médico obrigatório em toda legenda
- Toda afirmação médica precisa de DOI, mesmo que não citada no conteúdo
- Confirmar plano do mês antes de gerar copy
- Criar card no Notion só após aprovação explícita
