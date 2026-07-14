---
name: roteiros-roberta
description: >
  Produz roteiros de Video-Podcast e Reels para a Roberta Barni seguindo o fluxo
  de 6 fases com gates: checkpoint de base, mapeamento de resultados, definição
  de temas com auditoria anti-repetição ANTES de escrever, produção roteiro a
  roteiro (uma conversa por tema), consolidação, revisão estruturada e
  fechamento de loop com o feedback da Roberta. Não escreve nenhum roteiro sem
  auditoria de sobreposição aprovada. Use: "vamos fazer os roteiros da Roberta",
  "produzir o lote de roteiros", "roteiro de video-podcast da Roberta", "roteiro
  de reels da Roberta", /roteiros-roberta.
---

# /roteiros-roberta — Produção de Roteiros (Video-Podcast + Reels)

## Cliente
**Pasta:** `CLIENTE_Roberta-Barni/`
**Conselho:** CFP — Resolução 06/2019 (aplicação conforme orientação no CLIENTE.md)
**Formatos cobertos:** Video-Podcast (estúdio), Reels de câmera, Reels de caixinha de perguntas

## Dependências
- `CLIENTE_Roberta-Barni/CLIENTE.md` — temas, mix, persona, diretrizes CFP, links do acervo no Google Drive, estrutura do Notion
- `.claude/skills/voz-roberta/SKILL.md` — **documento de Princípios Globais.** Guia de voz, vocabulário proibido, estruturas vetadas, checklist. É atualizado a cada lote (Fase 0 e Fase 6) — sempre a versão mais recente de "o que a Roberta já corrigiu"
- Acervo no Google Drive (links no CLIENTE.md): legendas e roteiros aprovados, roteiros de gravação, conteúdos virais transcritos (B-roll, podcast, texto), transcrições de feedback da Roberta
- Planilha de análise de performance (Notion/SAFSM + mLabs) — link no CLIENTE.md
- Memória do Claude (`_contexto/` / auto-memory) — correções permanentes da Roberta já registradas

Este fluxo é o de **produção de roteiro** (o "como escrever certo, sem repetir e sem perder feedback"). Para decidir formatos/calendário do mês, ver `/planejar-roberta` — as duas skills se complementam: `/planejar-roberta` decide O QUE entra no mês, `/roteiros-roberta` executa a produção com o rigor de auditoria e fechamento de loop.

---

## Princípio central

Nenhum roteiro é escrito antes de:
1. A base estar atualizada (feedback do lote anterior incorporado).
2. O tema ter ângulo único confirmado (auditoria anti-repetição com status ✅).
3. O estudo dos aprovados e virais ter sido feito na própria conversa de produção daquele tema.

Regra de ouro da Fase 3: **uma conversa por tema.** Nunca produzir mais de um roteiro na mesma conversa — a qualidade cai e a voz dilui.

---

## FASE 0 — Checkpoint de base

Objetivo: garantir que a régua de voz está atualizada antes de gastar qualquer hora de produção.

1. Perguntar: "Antes de começar, tem feedback recente da Roberta (reunião, áudio, WhatsApp) que ainda não está registrado? Se tiver, me manda que eu incorporo antes de seguir."
2. **Fechamento do loop anterior:** verificar se o último lote entregue já teve o feedback da Roberta transcrito e as regras extraídas para `voz-roberta/SKILL.md` e para a memória do Claude (ver Fase 6). Se não teve, fazer isso agora, antes de iniciar o lote novo.
3. Reler `voz-roberta/SKILL.md` inteiro (vocabulário proibido, frases canônicas, estruturas vetadas, checklist). Se o feedback do lote anterior trouxe regra nova que ainda não está lá, atualizar o arquivo agora.

**⛔ GATE — não avançar sem isto:** se houver feedback da Roberta ainda não incorporado à base, o lote não começa. Resolver isso primeiro.

---

## FASE 1 — Mapeamento de resultados

Objetivo: decidir formatos e territórios temáticos com base em dados, não em intuição.

1. Puxar dados do período (Notion/SAFSM + mLabs, ver link no CLIENTE.md): alcance, compartilhamentos, salvamentos, novos seguidores e conversões por conteúdo.
2. Identificar os top performers do período e transcrever os que ainda não estiverem no acervo (Google Drive).
3. Atualizar a engenharia reversa dos virais se houver padrão novo: tipos de gancho, arco emocional, ritmo de frases, gatilhos de compartilhamento (identificação, cuidado com terceiro, curadoria pessoal).
4. Confirmar com a Gabriella o formato prioritário do lote e a regra de capa do momento (ex.: palavras luto, morte, dor, perda — ou variação vigente).

Entregar um diagnóstico curto (poucas linhas): formatos vencedores, territórios quentes, aprendizados novos. Só seguir para a Fase 2 depois disso.

---

## FASE 2 — Definição de temas + Auditoria Anti-Repetição

Esta é a fase crítica do processo. **A auditoria acontece ANTES de escrever qualquer roteiro** — nunca depois. Escrever um lote inteiro sem essa checagem prévia é o erro que este fluxo existe para eliminar.

### Passo 1 — Gerar a lista de temas

- Mix 50/50: metade viral/visceral (alto potencial de compartilhamento), metade com embasamento científico ou metodológico (estágios do Método 8 Estágios do Luto Sistêmico, estudos recentes sobre luto).
- Cada tema vem com: gancho sugerido, etapa do funil e justificativa de performance (ligar ao diagnóstico da Fase 1).
- Fontes: acervo do Google Drive + tendências da web (WebSearch) + temas e mix do CLIENTE.md + categorias/temas cadastrados no Notion.

### Passo 2 — Rodar a auditoria anti-repetição (antes de aprovar qualquer tema)

Cruzar cada tema proposto com TODO o acervo:
- Roteiros já publicados (acervo do Drive)
- Roteiros já aprovados aguardando gravação (Notion, fase "Aprovar texto" e posteriores)
- Legendas já publicadas

Apresentar sempre em tabela:

| Tema | Ângulo proposto | Diagnóstico |
|---|---|---|
| (ex.) Dor no peito | Somatização — sintomas físicos | ⚠️ Sobrepõe acervo de [período] → trocar ângulo p/ [sugestão] |
| (ex.) Luto Antecipatório | Despedida consciente | ✅ Único — aprovar |

Regras de decisão:
- ✅ Único → aprova.
- ⚠️ Sobreposição de ângulo → troca o ângulo (mantém o tema) OU substitui o tema por outro da lista.
- ⚠️ Temas complementares (mesmo território, mensagens diferentes, ex. dois tipos de luto parental) → podem coexistir, mas com espaçamento no calendário. Registrar a nota de espaçamento aqui mesmo, para a Fase 4 já nascer com isso marcado.

**⛔ GATE — não avançar sem isto:** nenhum tema entra na Fase 3 sem status ✅ na tabela. Apresentar a tabela completa e aguardar confirmação da Gabriella antes de iniciar qualquer produção.

---

## FASE 3 — Produção roteiro a roteiro

Regra de ouro: **uma conversa por tema.** Nunca produzir em lote na mesma conversa.

Toda conversa de produção começa por este ciclo — ele é acionado automaticamente sempre que a skill roda, eliminando o problema de primeiras versões fracas por falta de estudo da base.

### O ciclo por tema (7 passos)

1. **Estudo da base:** reler roteiros e legendas aprovados relacionados ao tema + a análise dos virais da Fase 1, ANTES de escrever qualquer linha. Sem exceção.
2. **Gancho travado:** definir headline e gancho primeiro — apresentar 2-3 opções curtas para escolha. "Luto" (ou palavra-dor equivalente) na primeira frase. Se a Gabriella já trouxer o gancho pronto, ele entra travado, sem alternativas.
3. **Rascunho completo:** roteiro de até 90s, frases curtas, `[PAUSA]` marcada nos pontos de virada emocional, experiência emocional antes do conceito, conceito emergindo organicamente (nunca anunciado como "bloco técnico").
4. **Edição incremental:** a Gabriella edita direto no texto e devolve. Trechos aprovados ficam travados — Claude entrega só a continuação ou o trecho flagrado. Nunca reescrita total sem pedido explícito.
5. **Embasamento verificado:** estudos pós-2022 com link verificável; citações de autores verificados tecidas como verdade emocional (citação primeiro, autoria depois). Autoria e referência completa ficam na legenda, não no roteiro falado.
6. **Legenda como nova camada:** estrutura abertura emocional → camada conceitual/sistêmica → princípio → consequência prática → fechamento com pergunta interativa variada (ver `voz-roberta`). Método, ciência e CTA moram na legenda, não no vídeo. CTA rotacionada — checar CTAs usados nos conteúdos mais recentes do calendário antes de repetir uma.
7. **Compliance de voz:** passar o checklist completo de `voz-roberta/SKILL.md` (vocabulário proibido, estruturas vetadas, "MAS" invalidante, "Eu vejo você" não é encerramento automático) antes de dar o roteiro por pronto.

Se for **reel de caixinha de perguntas**: a legenda não traz nova camada de conteúdo (o vídeo já faz isso) — deve ser mais sucinta, com foco só em CTA de engajamento.

---

## FASE 4 — Consolidação

1. Compilar todos os roteiros do lote num documento único, com marcação visual dos blocos de gravação, tempo estimado por bloco e notas técnicas de tom/pausa.
2. Checagem cruzada leve entre os roteiros do lote (a auditoria pesada já foi feita na Fase 2): variação de ganchos, de fechamentos e de CTAs entre conteúdos próximos no calendário. Aplicar aqui qualquer nota de espaçamento registrada na Fase 2.
3. Sugerir ordem de gravação em estúdio, agrupando por enquadramento/formato para economizar sessão.

---

## FASE 5 — Revisão estruturada (pré-entrega)

Cada roteiro passa pela auditoria de 4 critérios. Só entra no documento final o que passar nos 4:

1. **Linearidade e coerência do tema** — progressão limpa, sem saltos; transições contemplativas (cuidado com viradas motivacionais tipo "mas você é forte").
2. **Coerência com a abordagem** — os 3 pilares (transpessoal, sistêmico, clínico) integrados sem serem anunciados como bloco técnico. Experiência emocional primeiro, conceito depois.
3. **Reforço de autoridade** — autoridade demonstrada, não declarada: o conceito preciso que nomeia o que a persona sente e não sabia explicar.
4. **Compliance de vocabulário** — zero termos proibidos, zero estruturas vetadas (ver `voz-roberta`), capitalizações corretas (termos do Método sempre maiúsculos), CTA variada, sem travessão.

---

## FASE 6 — Entrega + Fechamento de loop

1. Entregar o documento consolidado para revisão da Roberta, com data registrada.
2. **Ao receber a revisão dela:** transcrever/subir o feedback para o acervo do projeto (Google Drive — doc de transcrições de feedback) na mesma semana.
3. **Extrair regras novas do feedback e atualizar, sem exceção:**
   - `voz-roberta/SKILL.md` (documento de Princípios Globais — vocabulário, estruturas, checklist)
   - Esta skill (`roteiros-roberta/SKILL.md`), se o feedback mudar o processo em si e não só a voz
   - Memória do Claude (auto-memory, tipo `feedback`) — para persistir entre conversas e sessões
   Correção da Roberta nunca fica presa numa conversa isolada.
4. Registrar no Notion o status de cada roteiro (aprovado / ajustar / vetado) para alimentar a Fase 0 do próximo lote.

**⛔ GATE — não avançar sem isto:** o próximo lote só começa quando o feedback deste estiver incorporado (volta à Fase 0 do próximo ciclo).

---

## Regras

- Nunca escrever um roteiro sem a tabela de auditoria anti-repetição da Fase 2 aprovada (status ✅) para aquele tema.
- Uma conversa por tema na Fase 3 — nunca lote na mesma conversa.
- Estudo da base (roteiros/legendas aprovados + virais) sempre no início do ciclo de cada tema, mesmo que pareça repetitivo.
- Gancho e headline aprovados antes do rascunho completo.
- Edição incremental: nunca reescrever trechos já aprovados sem pedido explícito.
- Método, ciência e CTA vivem na legenda; o vídeo é experiência emocional + conceito.
- Sem travessão (—), sem "MAS" invalidante, sem "a gente", sem "Muitas pessoas", sem "Dra." — ver checklist completo em `voz-roberta`.
- Todo feedback da Roberta pós-entrega vira regra registrada em até uma semana — nunca fica só na conversa onde foi dado.
- Diretrizes CFP sempre ativas: sem promessa de resultado/cura, sem "avaliação gratuita" (é "consulta"), sem depoimento que identifique paciente.
