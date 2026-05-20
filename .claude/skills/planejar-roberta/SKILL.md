---
name: planejar-roberta
description: >
  Planeja o calendário mensal de conteúdo da Roberta Barni.
  Analisa dados do mês anterior, pesquisa referências, gera copy completa para
  aprovação e só cria o card no Notion após confirmação.
  Referência às diretrizes do CFP disponível, aplicação conforme orientação no CLIENTE.md.
  Use: "vamos planejar o mês da Roberta", "montar o calendário da Roberta", /planejar-roberta.
---

# /planejar-roberta — Planejamento Mensal de Conteúdo

## Cliente
**Pasta:** `clientes/roberta-barni/`
**Conselho:** CFP — Resolução 06/2019 (aplicação conforme orientação no CLIENTE.md)
**Estrutura no Notion:** campo TEMAS (não linhas editoriais)

## Dependências
- `clientes/roberta-barni/CLIENTE.md` — temas, mix semanal, tom de voz, postura em relação ao CFP
- `clientes/roberta-barni/conhecimento/` — transcrições, lives, entrevistas, referências
- `_contexto/preferencias.md` — regras gerais de escrita
- `.claude/skills/planejar-conteudo/diretrizes-conselhos.md` — diretrizes do CFP (consulta)
- `.claude/skills/voz-roberta/SKILL.md` — guia completo de voz e estilo (ler antes de gerar qualquer copy)

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

Ler `clientes/roberta-barni/CLIENTE.md` e extrair:
- Temas com seus pesos e frequências
- Mix semanal (quantos por semana, por tema)
- Formatos ativos e canais
- Postura em relação às diretrizes do CFP

Ler materiais em `clientes/roberta-barni/conhecimento/` para calibrar linguagem e repertório da Roberta.

Consultar diretrizes do CFP em `.claude/skills/planejar-conteudo/diretrizes-conselhos.md` conforme orientação no CLIENTE.md.

---

### Fase 2 — Referências e pesquisa

Perguntar: "Quais referências você tem pra esse mês? Links, temas, transcrições ou quer pesquisar."

- **YouTube** → extrair transcrição: `yt-dlp --write-auto-sub --skip-download --sub-format vtt "[URL]"`
- **Link de post/artigo** → ler via WebFetch
- **Roteiro ou texto de base** → usar como estrutura e adaptar ao cliente
- **Tema livre** → gerar com base no CLIENTE.md
- **Pedido de pesquisa** → WebSearch com termos do tema

---

### Fase 3 — Plano do mês

Propor a distribuição de peças respeitando o mix de temas da Roberta:

> "Para a Roberta em [mês]:
> Semana 1: [peça — tema — formato] ...
> Começo pela semana 1?"

Aguardar confirmação antes de gerar qualquer copy.

---

### Fase 4 — Copy + aprovação + Notion

Para cada conteúdo, gerar e apresentar para aprovação:

---
**CONTEÚDO [número]**
**Formato:** [Carrossel / Reels / Card único / YouTube / Stories]
**Tema:** [nome do tema]
**Funil:** [Topo / Meio / Fundo / Topo-meio]
**Data prevista:** [semana X]

**Hook:**
[gancho que funciona na fala E na legenda ao mesmo tempo]

**Desenvolvimento:**
[carrossel: slide a slide | vídeo: roteiro por blocos com marcação de tempo | card: texto único]

**Legenda:**
[aprofunda o conteúdo — não resume nem repete]
Este conteúdo é informativo e não substitui o acompanhamento psicológico.

#hashtag1 #hashtag2 #hashtag3 #hashtag4 #hashtag5

**Referência visual:** [estilo ou referência sugerida]
**Instruções de design/edição:** [orientações específicas se necessário]

---

Perguntar: "Aprovado pra criar no Notion ou quer ajustar?"

Só criar o card no Notion após confirmação explícita. Ao criar, usar o campo **Tema** (não Linha editorial). Preencher: Título, Formato, Canais, Tipo de conteúdo, Funil, Data de Publicação, Cliente, Tema.

---

## Regras

- Ler `clientes/roberta-barni/conhecimento/` antes de escrever
- Tom de voz segue a Roberta, não a BrainWave
- Hook funciona com e sem som
- Legenda aprofunda — nunca resume
- 5 hashtags em todas as legendas
- Disclaimer obrigatório em toda legenda
- No Notion: usar campo TEMAS, não Linha editorial
- Confirmar plano do mês antes de gerar copy
- Criar card no Notion só após aprovação explícita
