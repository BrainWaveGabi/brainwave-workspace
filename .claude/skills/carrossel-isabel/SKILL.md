---
name: carrossel-isabel
description: >
  Cria carrosséis completos para a Dra. Isabel Carazzo: copy com fluxo de slides definido,
  compliance CFO automático, variação de layout entre slides e entre peças diferentes,
  integração com identidade visual e versão TikTok. Fase visual (HTML→PNG) requer
  Playwright instalado. Use: "faz um carrossel pra Isabel", "cria carrossel sobre [tema]",
  /carrossel-isabel.
---

# /carrossel-isabel — Carrossel Dra. Isabel Carazzo

## Dependências
- `CLIENTE_Dra-Isabel-Carazzo/CLIENTE.md` — linhas editoriais, tom de voz, compliance CFO
- `CLIENTE_Dra-Isabel-Carazzo/conhecimento/identidade-visual/` — diretrizes criativas
  *(se vazio, carregar via Drive MCP: file ID `1DqlnZ0ZuSsvfXSqLumZUMi6gRSKRytd7`)*
- `_contexto/preferencias.md` — regras gerais de escrita

## Output
```
CLIENTE_Dra-Isabel-Carazzo/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/
  carousel-text.md          ← copy aprovada + legenda + referência (se usada)
  instagram/
    slide-01.html → slide-01.png
    ...
  tiktok/ (se solicitado)
    slide-01.html → slide-01.png
    ...
```

---

## Workflow

### Fase 1 — Contexto e input

1. Ler `CLIENTE_Dra-Isabel-Carazzo/CLIENTE.md` — extrair:
   - Tom de voz e frases reais da Dra. Isabel
   - Linha editorial e funil do tema
   - Regras de conteúdo e compliance CFO
   - Identidade visual (cores, tipografia)

2. Identificar o input do usuário:
   - **Tema livre** → gerar com base no CLIENTE.md
   - **Link ou artigo** → ler via WebFetch e adaptar
   - **Ideia da skill pesquisar-ideias-isabel** → usar o ângulo e referência já definidos
   - **Roteiro base** → estruturar no fluxo de slides abaixo

3. Se a linha editorial e o funil não estiverem claros, perguntar antes de continuar.

---

### Fase 2 — Copy dos slides

**Fluxo obrigatório de slides (7–9 slides):**

| Slide | Função | Orientação |
|-------|---------|------------|
| **1 — Capa** | Para o scroll, define o tema | 3 opções de headline (máx. 8 palavras) + subtítulo curto. Usuário escolhe antes de continuar |
| **2 — Segunda headline + contexto** | Reforça o gancho, apresenta o problema ou a situação | 1 afirmação forte + 2-3 linhas de contextualização. Soa como a Dra. Isabel abrindo o assunto no consultório |
| **3–5 — Desenvolvimento** | Explica o mecanismo, mostra variação de casos | 1 ideia por slide, com lógica: "isso acontece porque…". Permitido ter "tem paciente que X… tem paciente que Y" |
| **6 — Contraponto** | Quebra expectativa ou desfaz crença errada | "Na teoria parece que… mas na prática não é bem assim." Reforça diferenciação clínica |
| **7–8 — Implicação** | O que isso muda para quem está lendo | Direto, sem clichê. Validação do paciente se pertinente |
| **Último — CTA** | Ação leve | Compartilhar / salvar / comentar. No orgânico, usar "Agende sua consulta pelo link na bio" apenas quando o contexto pedir claramente. Quando o CTA envolver agendamento, usar imagem da Dra. Isabel nesse slide (ver Fase 3) |

**Regras de texto:**
- Frases curtas e diretas — estilo fala, não artigo
- Sem travessão (—), sem excesso de pontuação
- Sem fórmulas genéricas: "você merece", "aprenda a", "descubra os segredos"
- CTA padrão: "Agende sua consulta" — nunca "avaliação gratuita"
- "Desconto" é proibido — usar "condição facilitada" ou "parcelamento sem juros"
- Compliance CFO: sem promessa de resultado, sem superlativo, sem comparação
- Antes e depois: só mencionar se houver TCLE assinado — perguntar antes de incluir

**Legenda (separada dos slides):**
- Aprofunda o conteúdo — nunca resume nem repete os slides
- Disclaimer obrigatório: *Este conteúdo é apenas informativo e não substitui a avaliação com um cirurgião-dentista.*
- 5 hashtags

**CHECKPOINT:** mostrar as 3 opções de capa + texto completo de todos os slides. Aguardar aprovação antes de seguir para Fase 3.

---

### Fase 3 — Visual (HTML → PNG)

> ⚠️ Esta fase requer Playwright instalado. Verificar com: `npx playwright --version`
> Se não estiver instalado: `npx playwright install chromium`

1. Carregar identidade visual:
   - Verificar se existe arquivo em `CLIENTE_Dra-Isabel-Carazzo/conhecimento/identidade-visual/`
   - Se vazio, carregar via Drive MCP: `mcp__claude_ai_Google_Drive__read_file_content` com file ID `1DqlnZ0ZuSsvfXSqLumZUMi6gRSKRytd7`
   - Extrair: paleta de cores, tipografia, elementos visuais recorrentes

2. Estilo geral: premium e humanizado. Alto padrão sem parecer frio. Tecnologia aparente com calor humano.

3. Criar HTMLs (1080×1350px, inline CSS, Google Fonts como única dependência externa)

**Variação de layout — obrigatória:**
- Nunca fazer todos os slides com layout idêntico
- Usar pelo menos 3 layouts diferentes por carrossel:
  - `texto-simples` — fundo sólido, texto centralizado
  - `destaque-numerico` — número ou dado grande em evidência
  - `citacao` — frase em destaque com barra lateral
  - `card-bordado` — card com borda e fundo levemente diferente
  - `imagem-fundo` — texto sobre imagem com gradiente e sombra forte
- **Variar também entre carrosseis diferentes** — não repetir a mesma sequência de layouts da peça anterior. Registrar os layouts usados no `carousel-text.md` para referência futura.

**Último slide — quando o CTA envolver agendamento ou contato:**
- Usar imagem da Dra. Isabel como elemento principal do layout
- Fluxo de escolha: primeiro `conhecimento/fotos-cliente/`, se vazio avisar e perguntar antes de criar

4. Salvar HTMLs em `CLIENTE_Dra-Isabel-Carazzo/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/instagram/`
5. Renderizar slide 1 primeiro:
   ```bash
   npx playwright screenshot --viewport-size=1080,1350 --full-page "file:///[caminho-absoluto]/slide-01.html" "slide-01.png"
   ```

**CHECKPOINT:** mostrar slide 1 renderizado. Se aprovado, renderizar os demais.

6. Renderizar slides restantes e salvar PNGs na mesma pasta.

---

### Fase 4 — Versão TikTok

Após todos os slides de Instagram serem renderizados e aprovados, **sempre perguntar:**
> "Quer adaptar para TikTok também? (formato vertical 1080×1920)"

Se sim:
- Duplicar os HTMLs do Instagram para a pasta `tiktok/`
- Adaptar cada arquivo:
  - `height: 1920px` no container principal
  - Aumentar padding vertical (mínimo 120px topo e base)
  - Aumentar fonte de corpo em ~15% para compensar a tela mais alta
  - Reposicionar elementos que ficarem mal distribuídos no vertical
- Renderizar:
  ```bash
  npx playwright screenshot --viewport-size=1080,1920 --full-page "file:///[caminho-absoluto]/slide-XX.html" "slide-XX.png"
  ```
- Salvar PNGs em `CLIENTE_Dra-Isabel-Carazzo/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/tiktok/`
- Mostrar slide 1 do TikTok antes de renderizar os demais — aguardar confirmação

---

### Fase 5 — Checagem CFO e salvar output

Antes de entregar, verificar:
- [ ] Promessa de resultado estético ou clínico? → reescrever
- [ ] Superlativo ou comparação? → reescrever
- [ ] Usando "Agende sua consulta" (não "avaliação gratuita")?
- [ ] Disclaimer na legenda?
- [ ] Antes e depois sem TCLE? → remover ou sinalizar

Salvar `carousel-text.md` em `CLIENTE_Dra-Isabel-Carazzo/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/` com:
- Copy de todos os slides
- Legenda completa
- Layouts utilizados (para variação na próxima peça)
- Briefing visual para o Igor (designer) se a Fase 3 não for executada

---

## Regras

- 3 opções de capa sempre — usuário escolhe antes de continuar
- Texto aprovado na Fase 2 não muda na Fase 3
- Sempre mostrar slide 1 antes de renderizar os demais
- Ajuste no visual → editar apenas o HTML alterado e re-renderizar só esse slide
- Registrar layouts usados por peça para garantir variação no próximo carrossel
- Tom de voz segue a Dra. Isabel, não a BrainWave
