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
- `CLIENTE_Dra-Isabel-Carazzo/conhecimento/identidade-visual/` — diretrizes criativas (PDF + logos disponíveis localmente)
- `CLIENTE_Dra-Isabel-Carazzo/conhecimento/producao-academica/artigos-e-publicacoes/` — artigos e publicações da Dra. Isabel
- `CLIENTE_Dra-Isabel-Carazzo/conhecimento/producao-academica/transcricoes/` — transcrições de vídeos e reuniões
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
| **1 — Capa** | Para o scroll, define o tema | 3 opções de headline. Pode ser frase (máx. 8 palavras) ou dado específico no formato "Tema: número antes → número hoje". Usuário escolhe antes de continuar |
| **2 — Segunda headline + introdução** | Reforça o gancho E abre o caminho para o desenvolvimento | Funciona como segunda headline E como ponte: conecta o dado ou afirmação da capa com o raciocínio que vem a seguir. Deve responder "por que isso acontece" em 2-3 linhas. Soa como a Dra. Isabel abrindo o assunto no consultório |
| **3–5 — Desenvolvimento** | Explica o mecanismo, mostra variação de casos | 1 ideia por slide, com lógica: "isso acontece porque…". Sem título nos cards de miolo — exceto em carrosseis estilo lista. Permitido ter "tem paciente que X… tem paciente que Y" |
| **6 — Contraponto** | Quebra expectativa ou desfaz crença errada | "Na teoria parece que… mas na prática não é bem assim." Reforça diferenciação clínica |
| **7–8 — Implicação** | O que isso muda para quem está lendo | Direto, sem clichê. Validação do paciente se pertinente |
| **Último — CTA** | Ação leve | Compartilhar / salvar / comentar. No orgânico, usar "Agende sua consulta pelo link na bio" apenas quando o contexto pedir claramente. Quando o CTA envolver agendamento, usar imagem da Dra. Isabel nesse slide (ver Fase 3) |

**Regras de texto:**
- Tom conversacional, não professoral. O leitor deve sentir que está ouvindo a Dra. Isabel, não lendo um artigo. Informativo e fluido ao mesmo tempo
- Cards de miolo: menos texto, mais ritmo. Cada card carrega uma ideia só, dita de forma natural. A legenda aprofunda com dados e informações adicionais que não cabem nos slides sem pesar o tom
- Frases curtas e diretas — estilo fala, não artigo
- Sem travessão (—), sem excesso de pontuação
- Consistência narrativa obrigatória: o conceito apresentado na capa deve se manter nos cards seguintes. Não introduzir ângulo diferente sem transição clara. Ex: capa fala de bruxismo do sono → desenvolvimento fala de bruxismo do sono, não mudar para bruxismo acordado sem justificar a conexão
- Sem fórmulas genéricas: "você merece", "aprenda a", "descubra os segredos"
- CTA padrão: "Agende sua consulta" — nunca "avaliação gratuita"
- "Desconto" é proibido — usar "condição facilitada" ou "parcelamento sem juros"
- Compliance CFO: sem promessa de resultado, sem superlativo, sem comparação
- Antes e depois: só mencionar se houver TCLE assinado — perguntar antes de incluir

**Legenda (separada dos slides):**
- Aprofunda o conteúdo — nunca resume nem repete os slides
- 5 hashtags
- Disclaimer obrigatório após as hashtags: *Este conteúdo tem caráter educativo e não substitui avaliação clínica individualizada.*

**CHECKPOINT:** mostrar as 3 opções de capa + texto completo de todos os slides. Aguardar aprovação antes de seguir para Fase 3.

---

### Fase 3 — Visual (HTML → PNG)

> ⚠️ Esta fase requer Playwright instalado. Verificar com: `npx playwright --version`
> Se não estiver instalado: `npx playwright install chromium`

1. Carregar identidade visual:
   - Logos disponíveis em `conhecimento/identidade-visual/Logomarca/`
   - Referências visuais de carrosséis aprovados: `conhecimento/referencias-criativas/`

2. Estilo geral: premium e humanizado. Alto padrão sem parecer frio. Tecnologia aparente com calor humano.

3. **Perguntas obrigatórias antes de criar os HTMLs:**

   a. "A capa vai ter foto da Dra. Isabel ou imagem temática?"
      - Com foto da Dra.: foto em destaque, headline sobreposta ou lado a lado
      - Com imagem temática: stock lifestyle ou conceitual com overlay dark navy (~65% opacidade)

   b. "Para o último slide, qual foto da Dra. Isabel usar?" — verificar opções em `conhecimento/fotos-cliente/Fotos profissionais 2024/` e indicar os nomes dos arquivos disponíveis

   c. Se o carrossel for sobre sedação consciente ou medo de dentista: "Quer estilo emocional com imagens vintage/preto-e-branco ou o padrão da marca?"

   d. Se houver slide com dado de estudo: confirmar se há print ou link disponível

4. Criar HTMLs (1080×1350px, inline CSS, Google Fonts como única dependência externa)

---

**Padrões visuais observados nas referências — aplicar em todos os carrosséis:**

**Uso da foto da Dra. Isabel:**
- Capa: opcional — definido na pergunta (3a) acima
- Slides de miolo: máximo 1 aparição, apenas em slides de autoridade ou transição narrativa
- Último slide: sempre quando o CTA envolve agendamento ou contato
  - Posição padrão: metade direita do slide, texto à esquerda
  - Elemento de texto recorrente antes do CTA: "E você?"
  - Foto disponível em `conhecimento/fotos-cliente/Fotos profissionais 2024/`

**Uso de imagens — duas modalidades:**

Modalidade 1 — como fundo (full-bleed):
- A imagem ocupa o fundo do slide. Pode ser stock ou foto real da Dra./clínica
- 1a. Com overlay: aplicar cor da paleta sobre a imagem (não necessariamente navy — pode ser qualquer cor da identidade visual). Válido para stock e fotos reais
- 1b. Sem overlay: usar apenas com fotos reais (nunca stock). Nesse caso o texto entra dentro de uma caixa/box para garantir leitura. Não aplicar texto solto sobre a imagem

Modalidade 2 — imagem recortada:
- A imagem é recortada (sem fundo) e posicionada como elemento visual no slide
- Usada principalmente nos slides de miolo
- Pode criar sensação de continuidade entre cards: a imagem começa em um card e termina no seguinte (efeito panorâmico)
- Elementos gráficos como caixas, linhas e formas geométricas seguem a mesma lógica de continuidade e podem ser usados junto ou separado das imagens

Sempre usar imagens de pessoas em situações emocionalmente reconhecíveis: cobrindo a boca, expressão de tensão, alívio, sorrindo. Evitar fotos anatômicas ou clínicas de baixa qualidade editorial.

**Variedade de elementos é obrigatória** — alternar entre as modalidades e com slides de texto puro. Não usar o mesmo tratamento em todos os slides do mesmo carrossel.

**Paleta por tipo de slide:**
- Texto puro: navy/teal escuro (#1B3A4B aprox.) + texto branco
- Dado de estudo em destaque: fundo branco ou claro, número grande, fonte do estudo em texto pequeno, logo no canto inferior direito
- Conteúdo emocional de sedação/medo: aceita imagens vintage ou preto-e-branco com overlay escuro — tom mais dramático que o padrão
- Conteúdo estético (facetas, clareamento, DSD): paleta mais clara, imagens de sorrisos, layout limpo e luminoso
- Destaques em gold/âmbar: títulos de capa e dados numéricos de impacto

**Variação de layout — obrigatória:**
- Nunca fazer todos os slides com layout idêntico
- Usar pelo menos 3 layouts diferentes por carrossel:
  - `texto-simples` — fundo sólido navy, texto centralizado em branco
  - `destaque-numerico` — número ou dado grande em evidência, fundo claro
  - `citacao` — frase em destaque com barra lateral ou aspas visuais
  - `split` — metade imagem / metade bloco de cor com texto
  - `imagem-fundo` — texto sobre imagem com overlay dark navy e gradiente
  - `card-bordado` — card com borda e fundo levemente diferente do slide
- **Variar também entre carrosseis diferentes** — não repetir a mesma sequência de layouts da peça anterior. Registrar os layouts usados no `carousel-text.md` para referência futura.

**Último slide — quando o CTA envolver agendamento ou contato:**
- Usar imagem da Dra. Isabel como elemento principal do layout
- Incluir "E você?" como elemento de texto antes do CTA
- Fluxo de escolha: primeiro `conhecimento/fotos-cliente/Fotos profissionais 2024/`, listar arquivos disponíveis e perguntar qual usar

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
- Briefing visual para o DESIGNER se a Fase 3 não for executada

---

## Regras

- 3 opções de capa sempre — usuário escolhe antes de continuar
- Texto aprovado na Fase 2 não muda na Fase 3
- Sempre mostrar slide 1 antes de renderizar os demais
- Ajuste no visual → editar apenas o HTML alterado e re-renderizar só esse slide
- Registrar layouts usados por peça para garantir variação no próximo carrossel
- Tom de voz segue a Dra. Isabel, não a BrainWave
