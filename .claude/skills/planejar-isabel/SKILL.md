---
name: planejar-isabel
description: >
  Planeja o calendário mensal de conteúdo da Dra. Isabel Carazzo.
  Analisa dados do mês anterior, pesquisa referências, gera copy completa para
  aprovação e só cria o card no Notion após confirmação.
  Diretrizes do CFO aplicadas automaticamente.
  Use: "vamos planejar o mês da Isabel", "montar o calendário da Isabel", /planejar-isabel.
---

# /planejar-isabel — Planejamento Mensal de Conteúdo

## Cliente
**Pasta:** `clientes/dra-isabel-carazzo/`
**Conselho:** CFO — Resolução CFO 196/2019 + CFO-SEC-271/2025
**Estrutura no Notion:** linhas editoriais

## Dependências
- `clientes/dra-isabel-carazzo/CLIENTE.md` — linhas editoriais, mix semanal, tom de voz
- `clientes/dra-isabel-carazzo/conhecimento/` — transcrições, lives, entrevistas, referências
- `clientes/dra-isabel-carazzo/conhecimento/producao-academica/artigos-e-publicacoes/` — artigos e publicações da Dra. Isabel
- `clientes/dra-isabel-carazzo/conhecimento/producao-academica/transcricoes/` — transcrições de vídeos e reuniões
- `_contexto/preferencias.md` — regras gerais de escrita
- `.claude/skills/planejar-conteudo/diretrizes-conselhos.md` — diretrizes do CFO

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

Ler `clientes/dra-isabel-carazzo/CLIENTE.md` e extrair:
- Linhas editoriais com pesos e frequências
- Mix semanal (quantos por semana, por linha)
- Formatos ativos e canais

Ler materiais em `clientes/dra-isabel-carazzo/conhecimento/` para calibrar linguagem e repertório da Dra. Isabel. Priorizar transcrições em `producao-academica/transcricoes/` e artigos em `producao-academica/artigos-e-publicacoes/` quando existirem.

Carregar diretrizes do CFO em `.claude/skills/planejar-conteudo/diretrizes-conselhos.md`.

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

Propor a distribuição de peças respeitando o mix de linhas editoriais da Dra. Isabel:

> "Para a Dra. Isabel em [mês]:
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
Este conteúdo é apenas informativo e não substitui a avaliação com um cirurgião-dentista.

#hashtag1 #hashtag2 #hashtag3 #hashtag4 #hashtag5

**Referência visual:** [estilo ou referência sugerida]
**Instruções de design/edição:** [orientações específicas se necessário]

---

Perguntar: "Aprovado pra criar no Notion ou quer ajustar?"

Só criar o card no Notion após confirmação explícita. Ao criar, preencher todas as propriedades: Título, Formato, Canais, Tipo de conteúdo, Funil, Data de Publicação, Cliente.

---

### Fase 5 — Checagem CFO

Antes de apresentar cada peça:
- Promessa de resultado estético? → reescrever
- Sensacionalismo ou comparação? → reescrever
- Há antes/depois? → confirmar se tem TCLE assinado antes de usar
- Vídeo do transcurso do procedimento? → não usar

---

## Regras

- Ler `clientes/dra-isabel-carazzo/conhecimento/` antes de escrever — priorizar `producao-academica/` quando existir conteúdo relevante
- Tom de voz segue a Dra. Isabel, não a BrainWave
- Hook funciona com e sem som
- Legenda aprofunda — nunca resume
- 5 hashtags em todas as legendas
- Disclaimer odontológico obrigatório em toda legenda
- Antes/depois só com TCLE confirmado — perguntar antes de incluir
- Confirmar plano do mês antes de gerar copy
- Criar card no Notion só após aprovação explícita
