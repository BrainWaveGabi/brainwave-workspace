---
name: pesquisar-ideias-isabel
description: >
  Pesquisa temas e referências para gerar ideias de conteúdo inéditas para a Dra. Isabel Carazzo.
  Cruza fontes científicas de odontologia, canal do YouTube da cliente, X/Twitter e buscas abertas
  com as linhas editoriais. Entrega lista de ideias para aprovação antes de qualquer produção.
  Use: "pesquisa ideias pra Isabel", "busca temas pra esse mês da Isabel", "o que tem de novo sobre
  implantes", "gera ideias sobre sedação consciente", /pesquisar-ideias-isabel.
---

# /pesquisar-ideias-isabel — Pesquisa de Temas e Ideias

## Cliente
**Arquivo de contexto:** `CLIENTE_Dra-Isabel-Carazzo/CLIENTE.md`
**Conselho:** CFO — Resolução CFO 196/2019 + CFO-SEC-271/2025
**Canais ativos:** Instagram, YouTube, LinkedIn

## Dependências
- `CLIENTE_Dra-Isabel-Carazzo/CLIENTE.md` — linhas editoriais, público, tom de voz, SEO prioritário
- `_contexto/preferencias.md` — regras gerais de escrita

---

## Workflow

### Fase 1 — Entender o pedido

Identificar:
1. **Tema ou linha editorial:** o usuário quer explorar uma linha específica (ex: sedação consciente, implantes, estética) ou pesquisa aberta?
2. **Formato de saída:** algum formato prioritário? (carrossel, reels, YouTube) — se não indicar, gerar ideias para qualquer formato
3. **Quantidade:** quantas ideias quer? Se não indicar, entregar 6 a 10

Se o pedido for vago demais, perguntar:
> "Quer explorar alguma linha editorial específica (sedação, implantes, estética) ou pesquisa aberta por novidades?"

---

### Fase 2 — Carregar contexto

Ler `CLIENTE_Dra-Isabel-Carazzo/CLIENTE.md` e extrair:
- Linhas editoriais com pesos e temas prioritários
- Tom de voz e público-alvo (medo de dentista, 30-60 anos, médio-alto)
- Termos SEO prioritários por funil (seção **SEO — Termos prioritários**)
- Regras de conteúdo e compliance CFO

---

### Fase 3 — Pesquisa multi-fonte

Fazer buscas em paralelo, cruzando fontes por relevância. Usar `WebSearch` e `WebFetch`.

#### 3a. Fontes científicas (prioritárias para conteúdo clínico)

Buscar estudos publicados nos últimos 2–3 anos sobre o tema. Fontes prioritárias:
- **PubMed** — `pubmed.ncbi.nlm.nih.gov` — buscar pelo tema em inglês
- **Journal of Dental Research** — `journals.sagepub.com/home/jdr`
- **Journal of Oral Implantology** — `meridian.allenpress.com/joi`
- **Clinical Oral Implants Research** — `onlinelibrary.wiley.com/journal/16000501`
- **SBPqO** — Sociedade Brasileira de Pesquisa Odontológica — `sbpqo.org.br`
- **CFO** — Conselho Federal de Odontologia — `cfo.org.br`
- **Harvard Health / JADA** — para linguagem acessível e evidência consolidada

Para cada achado relevante: anotar autores, título, revista, ano e DOI.

#### 3b. Canal do YouTube da cliente

Verificar o que já foi coberto para evitar repetição:
- Canal: `https://www.youtube.com/@DraIsabelCarazzo`
- Buscar vídeos recentes — identificar temas já tratados e lacunas relevantes

#### 3c. YouTube — canais de referência em odontologia

Buscar via `WebSearch` por: `site:youtube.com [tema] odontologia implante sedação`
- Identificar vídeos recentes (últimos 6 meses) com alto engajamento
- Se o usuário indicar URLs específicas de vídeo, extrair transcrição:
  ```
  yt-dlp --write-auto-sub --skip-download --sub-format vtt "[URL]"
  ```

#### 3d. X / Twitter

Buscar via `WebSearch` com operadores:
- `site:x.com OR site:twitter.com [tema] odontologia dentista` — discussões recentes
- Identificar: debates clínicos, dúvidas comuns de pacientes, tendências

#### 3e. Buscas abertas de tendência

Buscar o que está em alta para o público-alvo:
- `WebSearch`: `[tema] tendência 2025 2026 implante dentário medo dentista`
- `WebSearch`: `[tema] dúvida frequente paciente odontologia`
- `WebSearch`: `[tema] mito vs realidade implante sedação consciente`
- Identificar volumes de busca se disponíveis — cruzar com termos SEO do CLIENTE.md

---

### Fase 4 — Síntese e geração de ideias

Com base na pesquisa, gerar ideias que:
1. **Sejam inéditas** para o perfil da Dra. Isabel (checar canal dela pra não repetir)
2. **Encaixem nas linhas editoriais** com peso correto (~35% implantes, ~25% sedação, ~25% estética, ~15% educação)
3. **Tenham ângulo definido** — não "falar sobre implante", mas "o que acontece com o osso quando você adia o implante além do tempo"
4. **Respondam o estado emocional do público** — vergonha, medo, cansaço de adiar

**Critérios de qualidade da ideia:**
- Responde uma dúvida real que o paciente tem (não óbvia)
- Tem mecanismo explicável: "isso acontece porque…"
- Pode acolher a barreira emocional antes de apresentar a solução clínica
- Permite variação de perfis: "tem paciente que X… tem paciente que Y"
- Não é "5 dicas rápidas" — precisa ter profundidade
- Conecta com um dos termos SEO do CLIENTE.md quando pertinente

---

### Fase 5 — Apresentar para aprovação

Entregar lista de ideias neste formato:

---
**IDEIA [número]**
**Linha editorial:** [Sedação Consciente / Implantes e Reabilitação / Estética Dental / Educação e Prevenção]
**Funil:** [Topo / Meio / Fundo / Topo-meio]
**Formato sugerido:** [Carrossel / Reels / YouTube / Qualquer]
**Tema:** [tema central em uma frase]
**Ângulo:** [o que torna essa ideia específica e não óbvia]
**Gancho inicial (rascunho):** [frase inicial que abre o conteúdo]
**Referência base:** [Autor, Título abreviado, Revista, Ano — se aplicável]
**Por que funciona:** [1-2 linhas sobre por que essa ideia ressoa com o público-alvo]

---

Após entregar a lista:
> "Quais dessas ideias quer desenvolver? Posso começar pelo carrossel, roteiro ou legenda de qualquer uma."

Não desenvolver nenhuma ideia antes de ter confirmação explícita.

---

## Regras

- Não sugerir temas que a Dra. Isabel já cobriu recentemente (checar canal YouTube)
- Ângulo precisa ser específico: não "falar sobre sedação" mas "por que a maioria dos pacientes com medo não sabe que pode ser atendida sem sentir nada"
- Compliance CFO: sem promessa de resultado, sem superlativo, sem comparação
- CTA padrão: "Agende sua consulta" — nunca "avaliação gratuita"
- "Desconto" é proibido — usar "condição facilitada" ou "parcelamento sem juros"
- Apresentar ideias antes de desenvolver qualquer conteúdo
