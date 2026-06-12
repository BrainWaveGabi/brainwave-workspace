---
name: channel-analysis
description: >
  Use esta skill SEMPRE que for solicitada uma análise de resultados de canal digital (Instagram, YouTube, Ads)
  cruzada com objetivos de negócio, dados de conversão ou padrões de conteúdo. Triggers incluem:
  "análise de resultado", "relatório mensal", "o que está performando", "o que funciona no Instagram",
  "análise de conteúdo", "cruzar métricas com leads", "análise de canal", "relatório de performance",
  ou qualquer pedido que envolva entender o desempenho de conteúdo digital de um cliente.
  A skill acessa o Notion do cliente via MCP, lê dados de resultados e cards de conteúdo,
  cruza com planilha de leads/conversão e gera relatório DOCX estratégico.
  USAR MESMO que o pedido seja parcial (ex: "me fala o que está funcionando no Insta da Roberta").
---

# Skill: Análise de Resultados de Canais Digitais — BrainWave

## Visão Geral

Esta skill executa uma análise estratégica completa de canal digital para um cliente da BrainWave.
Ela foi projetada para responder à pergunta central: **o que está funcionando, por quê, e o que fazer a seguir.**

Fluxo principal:
1. Identificar cliente e período de análise
2. Buscar tabela de resultados no Notion (Instagram primeiro)
3. Buscar cards de conteúdo vinculados para entender copy/formato/tema
4. (Opcional) Ler planilha de leads/conversão se disponível
5. Executar análise em camadas (métricas → padrões → estratégia)
6. Gerar relatório DOCX

---

## Fase 1 — Coleta de Dados no Notion

### 1.1 Localizar a tabela de resultados

A tabela de resultados fica em uma **página separada** no Notion de cada cliente
(não dentro dos cards de conteúdo). Buscar pela página de resultados do canal.

**Colunas esperadas na tabela de resultados do Instagram:**
- `Título` — nome do conteúdo (vinculado ao card)
- `Tema` — categoria temática (ex: Reflexões, Luto parental, Conteúdo celebridade)
- `Formato` — Reels, Reel Podcast, Áudio Podcast, Carrossel, etc.
- `Data` — data de publicação
- `Visualizações` — métrica principal de alcance
- `Comentários`
- `Compartilhamentos`
- `Reposts`
- `Salvamentos`
- `Novos seguidores` — atribuídos ao post

**Importante:** Buscar TODAS as entradas do período analisado, não só os top performers.

### 1.2 Buscar cards de conteúdo vinculados

Para os **top 30% de posts** (por visualizações) e **bottom 20%** (piores performers),
acessar o card de conteúdo individual para extrair:
- Copy aprovada
- Legenda aprovada
- Notas do histórico de produção relevantes (briefing, direção criativa)
- Qualquer dado adicional de contexto (ex: post reativo, data especial, boost pago)

Não é necessário ler TODOS os cards — focar nos extremos para identificar padrões.

---

## Fase 2 — Análise em Camadas

Executar as análises abaixo em sequência. Cada camada alimenta a próxima.

### Camada 1: Ranking e Distribuição de Métricas

Calcular para o período:
- **Score de Engajamento Composto** por post:
  `(Comentários × 4) + (Compartilhamentos × 3) + (Salvamentos × 3) + (Reposts × 2) + (Novos Seguidores × 2)`
  *(pesos refletem intenção: comentar/salvar/compartilhar = ação deliberada)*
- Ordenar posts por: (a) Visualizações, (b) Score Composto, (c) Novos seguidores
- Identificar se o ranking muda muito entre as três ordenações — divergência é insight

Métricas agregadas do período:
- Total e média de cada métrica
- Distribuição por Formato (% de posts, % de visualizações totais)
- Distribuição por Tema

### Camada 2: Análise de Padrões por Formato

Para cada formato presente nos dados, calcular:
- Nº de posts
- Visualizações médias
- Score de engajamento médio
- Novos seguidores médios
- Melhor e pior post do formato

Pergunta a responder: **Quais formatos entregam alcance? Quais entregam engajamento? Quais convertem seguidores?**
Nem sempre é o mesmo formato — isso é um insight.

### Camada 3: Análise de Padrões por Tema

Mesma lógica da Camada 2, mas por Tema.
Pergunta adicional: **Existem temas que funcionam bem em um formato mas não em outro?**

### Camada 4: Análise Qualitativa de Copy (top e bottom performers)

Com os cards de conteúdo lidos na Fase 1.2, identificar:

**Nos top performers:**
- Abertura do post (gancho) — como começa? Pergunta? Afirmação forte? Identificação emocional?
- Estrutura da copy — sequência lógica ou emocional?
- CTA — tem? Qual tipo? (salvar, comentar, compartilhar, link na bio)
- Tema emocional central
- Especificidade vs. generalidade

**Nos bottom performers:**
- O que está faltando ou diferente?
- Eram posts reativos (datas comemorativas forçadas, tendências)?
- A copy é mais genérica, mais técnica ou mais longa?

**Output desta camada:** 3 a 5 padrões concretos identificados com exemplos.

### Camada 5: Cruzamento com Dados de Conversão (se disponível)

Se a planilha de leads foi fornecida:
- Filtrar leads do período analisado
- Identificar fonte de entrada (se disponível: Instagram, link na bio, stories, etc.)
- Verificar se picos de leads coincidem com posts de alto volume de visualizações ou alto engajamento
- Calcular taxa de conversão aproximada do período (leads ÷ novos seguidores gerados)

Se não houver dado de atribuição por post, trabalhar com correlação temporal:
"nos dias/semanas com maior engajamento, houve mais leads?"

### Camada 6: Análise Estratégica — Objetivos de Negócio

Esta é a camada mais importante. Conectar os dados aos objetivos do cliente.

Perguntar (ou recuperar do contexto/Notion do cliente):
- Qual o objetivo prioritário do canal neste período? (ex: crescimento de seguidores, autoridade, conversão para produto específico)
- O canal está servindo a esse objetivo ou derivando?

Avaliar:
- **Alinhamento:** Os conteúdos de maior performance estão no tema/posicionamento estratégico do cliente?
- **Risco de dependência:** O canal está muito dependente de um tipo de conteúdo? (ex: reposts de celebridades que performam bem mas não constroem marca própria)
- **Oportunidade não explorada:** Existe tema ou formato com poucos posts mas alta performance quando aparece?

---

## Fase 3 — Estrutura do Relatório DOCX

Gerar o relatório seguindo esta estrutura. Consultar a skill `docx` para geração do arquivo.

```
RELATÓRIO DE PERFORMANCE — [NOME CLIENTE]
[Canal] | [Mês/Ano]
Preparado por BrainWave Assessoria de Marketing

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. RESUMO EXECUTIVO
   — 3 a 5 bullets com os principais achados do mês
   — Destaque para o maior win e o maior gap do período

2. PANORAMA DO PERÍODO
   — Total de posts publicados
   — Métricas totais e médias (tabela)
   — Distribuição por formato (tabela)
   — Distribuição por tema (tabela)

3. TOP PERFORMERS DO MÊS
   — Top 5 posts por visualizações (tabela: título, formato, tema, métricas)
   — Top 5 posts por engajamento composto
   — Análise: o que eles têm em comum?

4. O QUE ESTÁ FUNCIONANDO
   — Formatos com melhor desempenho e por quê
   — Temas com melhor desempenho e por quê
   — Padrões de copy identificados nos top performers
   — Recomendação: o que repetir e como escalar

5. O QUE NÃO ESTÁ FUNCIONANDO
   — Posts/formatos/temas com baixa performance
   — Hipóteses sobre o porquê
   — Recomendação: o que ajustar, pausar ou testar diferente

6. DADOS DE CONVERSÃO (se disponível)
   — Leads do período e origem
   — Correlação com performance de conteúdo
   — Taxa de conversão estimada

7. ANÁLISE ESTRATÉGICA
   — O canal está servindo ao objetivo de negócio?
   — Riscos identificados (dependências, desvios de posicionamento)
   — Oportunidades identificadas

8. RECOMENDAÇÕES PARA O PRÓXIMO MÊS
   — 3 a 5 ações concretas e priorizadas
   — Formato: [AÇÃO] → [MOTIVO] → [COMO MEDIR]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Nota: Próxima análise comparativa disponível a partir do 2º mês.
```

---

## Fase 4 — Geração do DOCX

Consultar `/mnt/skills/public/docx/SKILL.md` para todas as regras de geração.

**Padrões visuais do relatório BrainWave:**
- Fonte: Arial
- Cor de destaque: `#1A1A2E` (títulos principais) e `#4A90D9` (destaques e tabelas header)
- Tamanho padrão: 12pt (corpo), 16pt (H1), 13pt (H2)
- Tabelas: sempre com header colorido `#4A90D9` com texto branco, linhas alternadas `#F5F5F5` / branco
- Margem: 1 polegada em todos os lados
- Página A4

**Nomenclatura do arquivo:**
`Relatorio_[NomeCliente]_Instagram_[MesAno].docx`
Ex: `Relatorio_RobertaBarni_Instagram_Maio2025.docx`

---

## Notas Operacionais

### Acesso ao Notion
- Usar MCP do Notion para acessar páginas e banco de dados do cliente
- A tabela de resultados é uma página separada, não o banco de conteúdo principal
- Para cards de conteúdo: buscar pelo título do post na base de conteúdo do cliente
- Se o acesso falhar em algum card, registrar como "card não acessado" e continuar

### Quando a planilha de leads não for fornecida
- Omitir a seção 6 do relatório
- Mencionar na seção 7 que a análise de conversão ficará disponível quando os dados forem fornecidos

### Expansão futura desta skill
- **YouTube:** adicionar métricas de watch time, retenção, CTR do thumbnail — ver `references/youtube.md` (a criar)
- **Ads:** adicionar CAC, ROAS, frequência, CTR — ver `references/ads.md` (a criar)
- **Comparativo de períodos:** implementar após 2+ meses de dados coletados

### Se dados estiverem incompletos
- Trabalhar com o que existe, sinalizar lacunas no relatório
- Nunca inventar dados ou médias sem base real nos dados fornecidos
- Preferir dizer "dados insuficientes para esta análise" a fazer suposições

---

## Checklist de Execução

Antes de gerar o relatório, confirmar:
- [ ] Tabela de resultados do Notion lida (todas as entradas do período)
- [ ] Cards dos top/bottom performers acessados
- [ ] Score de engajamento composto calculado para todos os posts
- [ ] Análise por formato completa
- [ ] Análise por tema completa
- [ ] Padrões de copy identificados (mínimo 3)
- [ ] Cruzamento com leads feito (se dados disponíveis)
- [ ] Recomendações são concretas e mensuráveis (não genéricas)
- [ ] DOCX gerado com nomenclatura correta
