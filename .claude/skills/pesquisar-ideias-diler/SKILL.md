---
name: pesquisar-ideias-diler
description: >
  Pesquisa temas e referências para gerar ideias de conteúdo inéditas para o Dr. Diler.
  Cruza fontes científicas, canais de YouTube indicados, X/Twitter e buscas abertas
  com as linhas editoriais do cliente. Entrega lista de ideias para aprovação antes
  de qualquer produção.
  Use: "pesquisa ideias pro Diler", "busca temas pra esse mês", "o que tem de novo sobre
  endometriose", "gera ideias sobre menopausa", /pesquisar-ideias-diler.
---

# /pesquisar-ideias-diler — Pesquisa de Temas e Ideias

## Cliente
**Arquivo de contexto:** `CLIENTE_Dr-Diler/CLIENTE.md`
**Conselho:** CFM — Resolução 2336/2023
**Canais ativos:** Instagram, YouTube, TikTok

## Dependências
- `CLIENTE_Dr-Diler/CLIENTE.md` — linhas editoriais, público, tom de voz, fontes específicas
- `_contexto/preferencias.md` — regras gerais de escrita

---

## Workflow

### Fase 1 — Entender o pedido

Identificar:
1. **Tema ou linha editorial:** o usuário quer explorar uma linha específica (ex: menopausa, cirurgia) ou pesquisa aberta?
2. **Formato de saída:** algum formato prioritário? (carrossel, reels, YouTube) — se não indicar, gerar ideias para qualquer formato
3. **Quantidade:** quantas ideias quer? Se não indicar, entregar 6 a 10

Se o pedido for vago demais, perguntar:
> "Quer explorar alguma linha editorial específica (sintomas, hormônios, cirurgia) ou pesquisa aberta por novidades?"

---

### Fase 2 — Carregar contexto

Ler `CLIENTE_Dr-Diler/CLIENTE.md` e extrair:
- Linhas editoriais com pesos e temas prioritários
- Tom de voz e público-alvo
- Fontes específicas listadas (seção **Fontes de pesquisa** — ver abaixo)
- Regras de conteúdo e compliance CFM

---

### Fase 3 — Pesquisa multi-fonte

Fazer buscas em paralelo, cruzando fontes por relevância. Usar `WebSearch` e `WebFetch`.

#### 3a. Fontes científicas (obrigatórias para conteúdo médico)

Buscar estudos publicados nos últimos 2–3 anos sobre o tema. Fontes prioritárias:
- **PubMed** — `pubmed.ncbi.nlm.nih.gov` — buscar pelo tema em inglês
- **ResearchGate** — `researchgate.net`
- **The New England Journal of Medicine** — `nejm.org`
- **The Lancet** — `thelancet.com`
- **Harvard Medical Review / Harvard Health** — `health.harvard.edu`
- **MedScape** — `medscape.com`
- **FEBRASGO** — federação brasileira de ginecologia e obstetrícia — `febrasgo.org.br`

Para cada achado relevante: anotar autores, título, revista, ano e DOI.

#### 3b. Fontes específicas do cliente

Ler a seção **Fontes de pesquisa** do `CLIENTE_Dr-Diler/CLIENTE.md`.
Se houver sites ou canais listados, acessar via `WebFetch` e extrair temas relevantes.

#### 3c. YouTube — canais de referência

Canais padrão para área de ginecologia/saúde feminina:
- Buscar via `WebSearch` por: `site:youtube.com [tema] [especialidade]`
- Identificar vídeos recentes (últimos 6 meses) com alto engajamento
- Se o usuário indicar URLs específicas de vídeo, extrair transcrição:
  ```
  yt-dlp --write-auto-sub --skip-download --sub-format vtt "[URL]"
  ```

Canais específicos do Dr. Diler (para entender o que já foi coberto):
- `https://www.youtube.com/@endotalk_drdiler` — verificar vídeos recentes pra evitar repetição

#### 3d. X / Twitter

Buscar via `WebSearch` com operadores:
- `site:x.com OR site:twitter.com [tema] [especialidade]` — discussões recentes
- Identificar: debates clínicos, dúvidas comuns de pacientes, tendências

#### 3e. Buscas abertas de tendência

Buscar o que está em alta para o público-alvo:
- `WebSearch`: `[tema] tendência 2025 2026 mulheres saúde`
- `WebSearch`: `[tema] dúvida frequente paciente`
- `WebSearch`: `[tema] mito vs realidade`
- Identificar volumes de busca se disponíveis (Google Trends, Answer The Public)

---

### Fase 4 — Síntese e geração de ideias

Com base na pesquisa, gerar ideias que:
1. **Sejam inéditas** para o perfil do Dr. Diler (checar canal dele pra não repetir)
2. **Tenham embasamento** em pelo menos uma referência científica identificada
3. **Encaixem nas linhas editoriais** com peso correto (70% topo / 20% meio / 10% fundo)
4. **Tenham ângulo definido** — não "falar sobre X", mas "por que X acontece ao contrário do que a paciente espera"

**Critérios de qualidade da ideia:**
- Responde uma dúvida real que a paciente tem (não óbvia)
- Tem mecanismo explicável: "isso acontece porque…"
- Permite variação de casos: "tem mulher que sente X, tem mulher que…"
- Pode quebrar expectativa ou desconstruir crença errada
- Não é "5 dicas rápidas" — precisa ter profundidade

---

### Fase 5 — Apresentar para aprovação

Entregar lista de ideias neste formato:

---
**IDEIA [número]**
**Linha editorial:** [Sintomas e Doenças / Hormônios e TRH / Cirurgia]
**Funil:** [Topo / Meio / Fundo]
**Formato sugerido:** [Carrossel / Reels / YouTube / Qualquer]
**Tema:** [tema central em uma frase]
**Ângulo:** [o que torna essa ideia específica e não óbvia]
**Gancho inicial (rascunho):** [frase inicial que abre o conteúdo]
**Referência base:** [Autor, Título abreviado, Revista, Ano]
**Por que funciona:** [1-2 linhas sobre por que essa ideia ressoa com o público-alvo]

---

Após entregar a lista:
> "Quais dessas ideias quer desenvolver? Posso começar pelo carrossel, roteiro ou legenda de qualquer uma."

Não desenvolver nenhuma ideia antes de ter confirmação explícita.

---

## Regras

- Toda ideia precisa ter pelo menos uma referência científica com DOI
- Referências: publicadas nos últimos 3 anos em canal reconhecido
- Não sugerir temas que o Dr. Diler já cobriu recentemente (checar canal YouTube)
- Distinções obrigatórias: endometriose ≠ adenomiose | climatério ≠ menopausa
- Sem "5 dicas" ou estrutura de lista superficial
- Ângulo precisa ser específico: não "falar sobre TRH" mas "por que médicos ainda têm medo de prescrever TRH mesmo com evidência atual"
- Compliance CFM: sem promessa de resultado, sem superlativo, sem comparação
- Apresentar ideias antes de desenvolver qualquer conteúdo
