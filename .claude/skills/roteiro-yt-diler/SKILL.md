---
name: roteiro-yt-diler
description: >
  Cria roteiros de YouTube para o Dr. Diler com SEO completo e embasamento científico.
  Analisa performance do canal, pesquisa temas com potencial de busca, propõe ideias
  para aprovação e só desenvolve o roteiro após confirmação do ângulo.
  Entrega: pacote SEO (tema, título, thumbnail, palavra-chave, tags, descrição) + roteiro.
  Aceita como entrada: tema livre, roteiro de base, transcrição ou link de referência.
  Diretrizes do CFM aplicadas. Use: "roteiro do Diler", "vídeo do YouTube do Diler", /roteiro-yt-diler.
---

# /roteiro-yt-diler — Roteiro de YouTube + SEO

## Cliente
**Pasta:** `clientes/dr-diler/`
**Conselho:** CFM — Resolução 2336/2023
**Canal:** YouTube do Dr. Diler

## Dependências
- `clientes/dr-diler/CLIENTE.md` — objetivos do canal, temas, tom de voz
- `clientes/dr-diler/conhecimento/` — transcrições, entrevistas, referências
- `_contexto/preferencias.md` — regras gerais de escrita
- `.claude/skills/planejar-conteudo/diretrizes-conselhos.md` — diretrizes do CFM

## Perfil SEO
Este agente opera como especialista em SEO para YouTube. Cada decisão de título, descrição, tags e thumbnail considera:
- **Intenção de busca** — o que a pessoa digita e o que espera encontrar
- **Volume x concorrência** — preferir termos com demanda real e baixa saturação
- **CTR** — título + thumbnail trabalham juntos para gerar clique
- **Retenção** — estrutura do roteiro impacta watch time e ranqueamento
- **Engajamento** — comentários, likes e compartilhamentos amplificam distribuição orgânica

---

## Workflow

### Fase 0 — Identificar o ponto de entrada

Verificar o que foi trazido:
- **Tema livre** → seguir para Fase 1
- **Roteiro de base ou inspiração** → usar como estrutura, adaptar ao canal e voz do Dr. Diler
- **Transcrição de entrevista ou live** → extrair blocos com mais potencial e propor ângulo
- **Link de vídeo** → extrair transcrição via yt-dlp: `yt-dlp --write-auto-sub --skip-download --sub-format vtt "[URL]"` e usar como referência

Se não trouxer nada: "Tem alguma referência ou parto de tema livre com base no canal?"

---

### Fase 1 — Análise do canal

Perguntar: "Quer analisar a performance do canal antes de definir o tema?"

Se sim, pedir dados de performance (views, retenção, temas que performaram, temas que caíram). Identificar:
- Vídeos com maior visualização e retenção
- Temas com potencial não explorado
- Lacunas nos temas centrais do canal

Se não, seguir com os temas do CLIENTE.md.

---

### Fase 2 — Pesquisa de temas, palavras-chave e referências científicas

Usar WebSearch para pesquisar:
- Volume de interesse nos temas do canal
- O que outros canais cobrem e o que está faltando
- Ângulos inovadores e pouco explorados

Para cada tema, identificar:
- **Palavra-chave principal** — boa demanda, baixa concorrência
- **Palavras-chave secundárias** — variações e termos relacionados
- **Intenção de busca** — o que quem pesquisa esse termo quer encontrar

**Embasamento científico obrigatório:** para todo conteúdo médico, localizar referência científica antes de escrever o roteiro. O estudo deve:
- Ter DOI
- Publicado nos últimos 3 anos
- Em canal reconhecido: PubMed, MedScape, ResearchGate, Harvard Medical Review, New England Journal of Medicine, The Lancet ou equivalente

Usar WebSearch/WebFetch para confirmar a referência antes de usar.

---

### Fase 3 — Proposta de ideias + aprovação

Apresentar 3 a 5 ideias:

> **Ideia 1**
> **Tema:** [assunto central]
> **Ângulo:** [por que é relevante e diferente]
> **Palavra-chave principal:** [termo alvo]
> **Por que ranqueia:** [justificativa — demanda, concorrência, intenção]
> **Duração estimada:** [X min]

Perguntar: "Qual você quer desenvolver? Ou ajusta algum ângulo?"

Só seguir após aprovação explícita.

---

### Fase 4 — Briefing do vídeo

Após aprovação, confirmar:
- Duração do vídeo
- CTA principal (inscrição, comentário, consulta, link)
- Informação específica que precisa entrar (dado, estudo, procedimento)

---

### Fase 5 — Pacote SEO

Entregar o pacote SEO para aprovação antes de escrever o roteiro:

---
**PACOTE SEO — [Tema]**

**Título:**
[Opção 1 — inclui palavra-chave principal, max 60 caracteres]
[Opção 2 — variação com ângulo diferente]

**Thumbnail:**
[Conceito: expressão, texto (max 3 palavras), cores, contraste]
[Por que converte: justificativa de CTR]

**Palavra-chave principal:** [termo exato]

**Tags:**
[tag 1], [tag 2], [tag 3], [tag 4], [tag 5], [tag 6], [tag 7], [tag 8], [tag 9], [tag 10]
*(mix de broad + específicas + variações da palavra-chave principal)*

**Descrição:**
[Primeiras 2-3 linhas: aparecem no resultado de busca — palavra-chave nas primeiras 25 palavras, frase que resume e gera clique]

[Corpo: 200-400 palavras com palavras-chave secundárias integradas naturalmente, timestamps dos blocos principais, CTA e links relevantes]

---

Apresentar para aprovação antes de escrever o roteiro.

---

### Fase 6 — Roteiro completo

Após aprovação do pacote SEO:

---
**ROTEIRO — [Título aprovado]**
**Duração estimada:** [X min]
**CTA:** [ação pedida]

**GANCHO**
[frase de abertura + promessa clara do vídeo — prende nos primeiros 30 segundos]

**DESENVOLVIMENTO**
[roteiro completo — texto corrido escrito para ser falado, organizado em blocos temáticos sem indicações de montagem ou câmera]

**CTA**
[chamada pra ação + frase de encerramento]

**Referência científica utilizada:**
[Autor, Título, Revista, Ano. DOI: xxx]

---

### Fase 7 — Checagem CFM

Antes de entregar:
- Promessa de resultado? → reescrever
- Superlativo ou comparação? → reescrever
- Afirmação médica sem referência científica? → buscar antes de entregar
- Usando "consulta" (não "avaliação gratuita")? → corrigir se necessário

---

## Regras

- Ler `clientes/dr-diler/conhecimento/` antes de escrever
- Tom de voz segue o Dr. Diler, não a BrainWave
- Roteiro escrito para ser falado — frases naturais, não texto de blog
- Sem indicações de montagem, câmera ou edição no roteiro
- Gancho estruturado para prender nos primeiros 30 segundos
- Toda afirmação médica precisa de DOI, mesmo que não citada explicitamente no vídeo
- Pacote SEO aprovado antes de escrever o roteiro
- Só desenvolver roteiro após aprovação da ideia E do pacote SEO
- Aceita qualquer ponto de entrada: tema livre, base da Gabi, transcrição ou link
