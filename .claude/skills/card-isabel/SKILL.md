---
name: card-isabel
description: >
  Cria cards estáticos e capas de reels para a Dra. Isabel Carazzo. Começa perguntando o formato,
  gera copy e HTML estilizado com a identidade visual, renderiza em PNG via Playwright.
  Use: "faz um card pra Isabel", "cria capa de reel da Isabel", "card sobre [tema]", /card-isabel.
---

# /card-isabel — Card Estático e Capa de Reels

## Dependências

- `CLIENTE_Dra-Isabel-Carazzo/CLIENTE.md` — tom de voz, compliance CFO, linhas editoriais
- `CLIENTE_Dra-Isabel-Carazzo/conhecimento/identidade-visual/` — cores, tipografia, fluxo de imagem
  *(se vazio, carregar via Drive MCP: file ID `1DqlnZ0ZuSsvfXSqLumZUMi6gRSKRytd7`)*
- `_contexto/preferencias.md` — regras gerais de escrita

## Output

**Card estático:**
```
CLIENTE_Dra-Isabel-Carazzo/conteudo/estaticos/cards/[tema-YYYYMMDD]/
  card-text.md       ← copy aprovada + legenda
  card.html
  card.png
```

**Capa de reels:**
```
CLIENTE_Dra-Isabel-Carazzo/conteudo/estaticos/capas/reels/[tema-YYYYMMDD]/
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

Ler `CLIENTE_Dra-Isabel-Carazzo/CLIENTE.md` e identidade visual antes de qualquer produção.

---

### Fase 2 — Copy

#### Card estático

Uma peça, uma ideia. Definir:
- **Tipo de card:**
  - `educacional` — dado, fato clínico ou explicação com 1-2 frases de contexto
  - `insight` — afirmação ou ponto de vista da Dra. Isabel (tom de consultório)
  - `dúvida frequente` — pergunta do paciente + resposta direta
  - `lista rápida` — 3-5 itens com lógica clara (não bullet points soltos)
  - `citação` — frase de destaque atribuída à Dra. Isabel

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
- Imagem da Dra. Isabel obrigatória (ver Fase 3)
- Texto posicionado na metade superior (zona segura de visualização no feed)
- Fundo com identidade visual — nunca fundo branco puro ou sem tratamento

**Regras de texto (ambos os formatos):**
- Sem travessão (—), sem excesso de pontuação
- Sem fórmulas genéricas: "você merece", "aprenda a", "descubra"
- CTA padrão: "Agende sua consulta" — nunca "avaliação gratuita" (Isabel cobra pela consulta)
- "Desconto" é proibido — usar "condição facilitada" ou "parcelamento sem juros"
- Compliance CFO: sem promessa de resultado, sem superlativo, sem comparação
- Antes e depois: só mencionar se houver TCLE assinado — perguntar antes de incluir
- Disclaimer na legenda: *Este conteúdo é apenas informativo e não substitui a avaliação com um cirurgião-dentista.*

**CHECKPOINT:** mostrar a copy completa (texto do card + legenda). Aguardar aprovação antes de seguir para Fase 3.

---

### Fase 3 — Visual (HTML → PNG)

> ⚠️ Requer Playwright. Verificar com: `npx playwright --version`
> Se não instalado: `npx playwright install chromium`

Carregar identidade visual:
1. Verificar se existe arquivo em `CLIENTE_Dra-Isabel-Carazzo/conhecimento/identidade-visual/`
2. Se vazio, carregar via Drive MCP: `mcp__claude_ai_Google_Drive__read_file_content` com file ID `1DqlnZ0ZuSsvfXSqLumZUMi6gRSKRytd7`
3. Extrair: paleta de cores, tipografia, elementos visuais recorrentes

Estilo geral: premium e humanizado. Alto padrão sem parecer frio. Tecnologia aparente com calor humano.

#### Dimensões por formato

| Formato | Dimensões | Viewport Playwright |
|---------|-----------|---------------------|
| Card estático | 1080×1080px | `--viewport-size=1080,1080` |
| Capa de reels | 1080×1920px | `--viewport-size=1080,1920` |

#### Imagem da Dra. Isabel

**Capa de reels:** imagem obrigatória.
**Card estático:** usar quando o tipo de card se beneficiar de presença humana (ex: citação, insight pessoal). Opcional nos demais tipos.

Fluxo de escolha:
1. Foto indicada pelo usuário → usar
2. Sem indicação → buscar em `CLIENTE_Dra-Isabel-Carazzo/conhecimento/fotos-cliente/`
3. Pasta vazia → avisar e perguntar antes de criar o visual

#### Layouts disponíveis

- `texto-simples` — fundo sólido, texto centralizado, sem foto
- `destaque-numerico` — número ou dado grande em evidência
- `citacao` — frase grande com barra lateral, foto opcional à direita ou ao fundo
- `imagem-fundo` — foto como fundo com gradiente e sombra forte no texto (padrão para capa de reels)
- `card-bordado` — card com borda e fundo levemente diferente

Não repetir o mesmo layout em peças diferentes da mesma sessão.

#### Renderização

```bash
npx playwright screenshot --viewport-size=[W,H] --full-page "file:///[caminho-absoluto]/card.html" "card.png"
```

**CHECKPOINT:** mostrar o PNG gerado. Aguardar aprovação antes de salvar o output final.

Se o usuário pedir ajuste visual: editar apenas o HTML e re-renderizar.

---

### Fase 4 — Checagem CFO e salvar output

Antes de entregar, verificar:
- [ ] Promessa de resultado estético ou clínico? → reescrever
- [ ] Superlativo ou comparação? → reescrever
- [ ] Usando "Agende sua consulta" (não "avaliação gratuita")?
- [ ] Disclaimer na legenda?
- [ ] Antes e depois sem TCLE? → remover ou sinalizar

Salvar `card-text.md` na pasta de destino com:
- Texto do card aprovado
- Legenda completa
- Layout utilizado (para variação na próxima peça)

---

## Regras

- Sempre perguntar o formato antes de qualquer produção
- Texto aprovado na Fase 2 não muda na Fase 3
- Imagem da Dra. Isabel obrigatória em capas de reels — avisar se não tiver disponível
- Ajuste visual → editar apenas o HTML alterado e re-renderizar
- Registrar layout usado para garantir variação entre peças
- Tom de voz segue a Dra. Isabel, não a BrainWave
