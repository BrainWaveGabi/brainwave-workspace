---
name: carrossel-diler
description: >
  Cria carrosséis completos para o Dr. Diler: copy com fluxo de slides definido,
  compliance CFM automático, variação de layout entre slides e entre peças diferentes,
  integração com identidade visual e versão TikTok. Fase visual (HTML→PNG) requer
  Playwright instalado. Use: "faz um carrossel pro Diler", "cria carrossel sobre [tema]",
  /carrossel-diler.
---

# /carrossel-diler — Carrossel Dr. Diler

## Dependências
- `CLIENTE_Dr-Diler/CLIENTE.md` — linhas editoriais, tom de voz, compliance CFM, identidade visual
- `CLIENTE_Dr-Diler/conhecimento/identidade-visual/` — diretrizes criativas e referências visuais
- `_contexto/preferencias.md` — regras gerais de escrita

## Output
```
CLIENTE_Dr-Diler/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/
  carousel-text.md          ← copy aprovada + legenda + referência científica
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

1. Ler `CLIENTE_Dr-Diler/CLIENTE.md` — extrair:
   - Tom de voz e marcadores reais de fala
   - Linha editorial e funil do tema
   - Regras de conteúdo e compliance CFM
   - Identidade visual (cores, tipografia)

2. Identificar o input do usuário:
   - **Tema livre** → gerar com base no CLIENTE.md
   - **Link ou artigo** → ler via WebFetch e adaptar
   - **Ideia da skill pesquisar-ideias-diler** → usar o ângulo e referência já definidos
   - **Roteiro base** → estruturar no fluxo de slides abaixo

3. Se a linha editorial e o funil não estiverem claros, perguntar antes de continuar.

---

### Fase 2 — Copy dos slides

**Fluxo obrigatório de slides (7–9 slides):**

| Slide | Função | Orientação |
|-------|---------|------------|
| **1 — Capa** | Para o scroll, define o tema | 3 opções de headline (máx. 8 palavras) + subtítulo curto. Usuário escolhe antes de continuar |
| **2 — Segunda headline + contexto** | Reforça o gancho, apresenta o problema ou a situação | 1 afirmação forte + 2-3 linhas de contextualização. Soa como o Dr. Diler abrindo o assunto no consultório |
| **3–5 — Desenvolvimento** | Explica o mecanismo, mostra variação de casos | 1 ideia por slide, com lógica: "isso acontece porque…". Permitido ter "tem mulher que X… tem mulher que Y" |
| **6 — Contraponto** | Quebra expectativa ou desfaz crença errada | "Na teoria parece que… mas na prática não é bem assim." Reforça diferenciação clínica |
| **7–8 — Implicação** | O que isso muda para quem está lendo | Direto, sem clichê. Validação da paciente se pertinente |
| **Último — CTA** | Ação leve | Compartilhar / salvar / comentar. Nunca "agende agora" no orgânico |

**Regras de texto:**
- Frases curtas e diretas — estilo fala, não artigo
- Sem travessão (—), sem excesso de pontuação
- Sem fórmulas genéricas: "você merece", "aprenda a", "descubra os segredos"
- Distinções clínicas obrigatórias: endometriose ≠ adenomiose | climatério ≠ menopausa
- Toda afirmação médica precisa ter referência científica (DOI, últimos 3 anos)
- Compliance CFM: sem promessa de resultado, sem superlativo, sem comparação

**Legenda (separada dos slides):**
- Aprofunda o conteúdo — nunca resume nem repete os slides
- Disclaimer obrigatório: *Este conteúdo é apenas informativo e não substitui a consulta médica.*
- 5 hashtags

**CHECKPOINT:** mostrar as 3 opções de capa + texto completo de todos os slides. Aguardar aprovação antes de seguir para Fase 3.

---

### Fase 3 — Visual (HTML → PNG)

> ⚠️ Esta fase requer Playwright instalado. Verificar com: `npx playwright --version`
> Se não estiver instalado: `npx playwright install chromium`

1. Ler `CLIENTE_Dr-Diler/conhecimento/identidade-visual/` para aplicar identidade visual
2. Se não houver arquivo de identidade visual, usar os valores do CLIENTE.md:
   - Cores: `#C19B43` (dourado principal), `#EBCA7D` (dourado claro), `#FFF7EC` (creme fundo), `#000000`, `#FFFFFF`
   - Tipografia headlines: Antonio / Bebas Neue / Montserrat
   - Tipografia corpo: Montserrat
   - Barra dourada `#C19B43` no rodapé de todas as peças
   - Estilo layered: fundo com desfoque/transparência ~50%, imagem principal com maior contraste

3. Criar HTMLs (1080×1350px, inline CSS, Google Fonts como única dependência externa)

**Variação de layout — obrigatória:**
- Nunca fazer todos os slides com layout idêntico
- Usar pelo menos 3 layouts diferentes por carrossel:
  - `texto-simples` — fundo sólido, texto centralizado
  - `destaque-numerico` — número ou dado grande em evidência
  - `citacao` — frase em destaque com barra lateral dourada
  - `card-bordado` — card com borda dourada e fundo levemente diferente
  - `imagem-fundo` — texto sobre imagem com gradiente e sombra forte
- **Variar também entre carrosseis diferentes** — não repetir a mesma sequência de layouts da peça anterior. Registrar os layouts usados no `carousel-text.md` para referência futura.

4. Salvar HTMLs em `CLIENTE_Dr-Diler/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/instagram/`
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
- Salvar PNGs em `CLIENTE_Dr-Diler/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/tiktok/`
- Mostrar slide 1 do TikTok antes de renderizar os demais — aguardar confirmação

---

### Fase 5 — Checagem CFM e salvar output

Antes de entregar, verificar:
- [ ] Promessa de resultado? → reescrever
- [ ] Superlativo ou comparação? → reescrever
- [ ] Afirmação médica sem referência? → buscar DOI antes de entregar
- [ ] Usando "consulta" (não "avaliação gratuita")?
- [ ] Disclaimer médico na legenda?

Salvar `carousel-text.md` em `CLIENTE_Dr-Diler/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/` com:
- Copy de todos os slides
- Legenda completa
- Referência científica (Autor, Título, Revista, Ano, DOI)
- Layouts utilizados (para variação na próxima peça)
- Briefing visual para a Luana (designer) se a Fase 3 não for executada

---

## Regras

- 3 opções de capa sempre — usuário escolhe antes de continuar
- Texto aprovado na Fase 2 não muda na Fase 3
- Sempre mostrar slide 1 antes de renderizar os demais
- Ajuste no visual → editar apenas o HTML alterado e re-renderizar só esse slide
- Registrar layouts usados por peça para garantir variação no próximo carrossel
- Tom de voz segue o Dr. Diler, não a BrainWave
- Referência científica obrigatória com DOI, publicada nos últimos 3 anos
