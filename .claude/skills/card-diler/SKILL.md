---
name: card-diler
description: >
  Cria cards estáticos e capas de reels para o Dr. Diler. Começa perguntando o formato,
  gera copy e HTML estilizado com a identidade visual, renderiza em PNG via Playwright.
  Use: "faz um card pro Diler", "cria capa de reel", "card sobre [tema]", /card-diler.
---

# /card-diler — Card Estático e Capa de Reels

## Dependências

- `CLIENTE_Dr-Diler/CLIENTE.md` — tom de voz, compliance CFM, linhas editoriais
- `CLIENTE_Dr-Diler/conhecimento/identidade-visual/identidade-visual.md` — cores, tipografia, fluxo de imagem
- `_contexto/preferencias.md` — regras gerais de escrita

## Output

**Card estático:**
```
CLIENTE_Dr-Diler/conteudo/estaticos/cards/[tema-YYYYMMDD]/
  card-text.md       ← copy aprovada + legenda
  card.html
  card.png
```

**Capa de reels:**
```
CLIENTE_Dr-Diler/conteudo/estaticos/capas/reels/[tema-YYYYMMDD]/
  card-text.md       ← texto do card + legenda do reel
  capa.html
  capa.png
```

---

## Workflow

### Fase 1 — Formato e contexto

**Sempre começar perguntando o formato:**
> "Card estático (feed 1080×1080) ou capa de reels (1080×1920)?"

Após a resposta, perguntar:
> "Qual é o tema ou conteúdo?"

Se o usuário já trouxe o tema junto com o formato, pular a segunda pergunta e seguir direto.

Ler `CLIENTE_Dr-Diler/CLIENTE.md` e `identidade-visual.md` antes de qualquer produção.

---

### Fase 2 — Copy

#### Card estático

Uma peça, uma ideia. Definir:
- **Tipo de card:**
  - `educacional` — dado, estatística ou fato clínico com 1-2 frases de contexto
  - `insight` — afirmação ou ponto de vista do Dr. Diler (tom de consultório)
  - `dúvida frequente` — pergunta da paciente + resposta direta
  - `lista rápida` — 3-5 itens com lógica clara (não bullet points soltos)
  - `citação` — frase de destaque atribuída ao Dr. Diler

Gerar:
- **Texto principal do card** — máx. 30 palavras (frases diretas, estilo fala)
- **Subtítulo ou complemento** — opcional, máx. 15 palavras
- **Legenda** — aprofunda o tema, 3-5 linhas, disclaimer obrigatório, 5 hashtags

#### Capa de reels

A capa precisa funcionar como thumbnail: parar o scroll e deixar claro o tema do reel.

Gerar:
- **Headline da capa** — máx. 8 palavras, gancho direto (mesmo texto ou adaptação do gancho do reel)
- **Subtítulo** — opcional, máx. 5 palavras, apenas se complementar sem repetir
- **Legenda do reel** — segue as mesmas regras do card estático

Regras para capa de reels:
- Imagem do Dr. Diler obrigatória (ver Fase 3)
- Texto posicionado na metade superior (zona segura de visualização no feed)
- Fundo com identidade visual — nunca fundo branco puro ou sem tratamento

**Regras de texto (ambos os formatos):**
- Sem travessão (—), sem excesso de pontuação
- Sem fórmulas genéricas: "você merece", "aprenda a", "descubra"
- Distinções clínicas: endometriose ≠ adenomiose | climatério ≠ menopausa
- Compliance CFM: sem promessa de resultado, sem superlativo, sem comparação
- Disclaimer na legenda: *Este conteúdo é apenas informativo e não substitui a consulta médica.*

**CHECKPOINT:** mostrar a copy completa (texto do card + legenda). Aguardar aprovação antes de seguir para Fase 3.

---

### Fase 3 — Visual (HTML → PNG)

> ⚠️ Requer Playwright. Verificar com: `npx playwright --version`
> Se não instalado: `npx playwright install chromium`

Ler `identidade-visual.md` para aplicar:
- Cores: `#C19B43` (dourado principal), `#EBCA7D` (dourado claro), `#FFF7EC` (creme fundo), `#000000`, `#FFFFFF`
- Tipografia headlines: Antonio / Bebas Neue / Montserrat
- Tipografia corpo: Montserrat
- Barra dourada `#C19B43` no rodapé — obrigatório em todas as peças

#### Dimensões por formato

| Formato | Dimensões | Viewport Playwright |
|---------|-----------|---------------------|
| Card estático | 1080×1080px | `--viewport-size=1080,1080` |
| Capa de reels | 1080×1920px | `--viewport-size=1080,1920` |

#### Imagem do Dr. Diler

**Capa de reels:** imagem obrigatória.
**Card estático:** usar quando o tipo de card se beneficiar de presença humana (ex: citação, insight pessoal). Opcional nos demais tipos.

Fluxo de escolha (conforme `identidade-visual.md`):
1. Foto indicada pelo usuário → usar
2. Sem indicação → buscar em `conhecimento/fotos-cliente/`
3. Pasta vazia → buscar na subpasta mais recente do Drive (ver link em `identidade-visual.md`)
4. Nenhuma disponível → avisar e perguntar antes de criar o visual

#### Layouts disponíveis

- `texto-simples` — fundo sólido, texto centralizado, sem foto
- `destaque-numerico` — número ou dado grande em evidência
- `citacao` — frase grande com barra lateral dourada, foto opcional à direita ou ao fundo
- `imagem-fundo` — foto como fundo com gradiente escuro e sombra forte no texto (padrão para capa de reels)
- `card-bordado` — card com borda dourada e fundo levemente diferente

Não repetir o mesmo layout em peças diferentes da mesma sessão.

#### Renderização

```bash
npx playwright screenshot --viewport-size=[W,H] --full-page "file:///[caminho-absoluto]/card.html" "card.png"
```

**CHECKPOINT:** mostrar o PNG gerado. Aguardar aprovação antes de salvar o output final.

Se o usuário pedir ajuste visual: editar apenas o HTML e re-renderizar.

---

### Fase 4 — Checagem CFM e salvar output

Antes de entregar, verificar:
- [ ] Promessa de resultado? → reescrever
- [ ] Superlativo ou comparação? → reescrever
- [ ] Usando "consulta" (não "avaliação gratuita")?
- [ ] Disclaimer na legenda?
- [ ] Barra dourada no rodapé?

Salvar `card-text.md` na pasta de destino com:
- Texto do card aprovado
- Legenda completa
- Layout utilizado (para variação na próxima peça)

---

## Regras

- Sempre perguntar o formato antes de qualquer produção
- Texto aprovado na Fase 2 não muda na Fase 3
- Imagem do Dr. Diler obrigatória em capas de reels — avisar se não tiver disponível
- Ajuste visual → editar apenas o HTML alterado e re-renderizar
- Registrar layout usado para garantir variação entre peças
- Tom de voz segue o Dr. Diler, não a BrainWave
