---
name: carrossel
description: >
  Cria carrosséis para qualquer cliente. Recebe a copy pronta e monta os slides
  com identidade visual do cliente, imagens do banco de imagens do cliente e
  variação de layout. Formato Instagram 1080×1350px com versão TikTok opcional.
  Use: "faz um carrossel", "monta o carrossel", /carrossel.
---

# /carrossel — Criação de Carrossel

## Dependências
- `CLIENTE_[nome]/CLIENTE.md` — identidade visual, compliance, pasta de banco de imagens, disclaimer
- `_contexto/preferencias.md` — regras gerais de escrita
- Playwright: `npx playwright screenshot` para renderizar HTMLs em PNG

---

## Workflow

### Fase 1 — Identificar o cliente

Se o cliente não foi informado na chamada da skill, perguntar:
> "Para qual cliente é esse carrossel?"

Com o cliente definido:
1. Ler `CLIENTE_[nome]/CLIENTE.md` — extrair:
   - Identidade visual: cores, tipografia, logos
   - Pasta do banco de imagens (ex: `conhecimento/banco-de-imagens/`)
   - Conselho profissional e regras de compliance (CFM, CFO, CFP, etc.)
   - Disclaimer obrigatório, se houver
   - Tom de voz e marcadores reais de fala

---

### Fase 2 — Receber a copy

Pedir ao usuário:
> "Manda a copy dos slides. Pode ser em texto corrido — vou dividir em slides."

Com a copy recebida:
- Dividir em slides conforme o volume de texto (sem número fixo — depende da copy)
- Identificar se o último slide tem CTA de agendamento/contato

---

### Fase 3 — Definir imagens

Para cada slide, listar os arquivos disponíveis na pasta de banco de imagens do cliente e perguntar qual usar:
> "Para o slide [N] com o texto '[trecho]', quais imagens estão disponíveis: [lista de arquivos]. Qual você quer usar?"

Se não conseguir interpretar os arquivos de imagem para sugerir o melhor match com o texto, pedir orientação diretamente:
> "Não consigo visualizar as imagens para sugerir. Me diz qual arquivo combina com esse slide."

**Último slide com CTA de agendamento:**
- Perguntar qual foto do profissional usar (listar opções disponíveis em `conhecimento/fotos-cliente/` ou pasta indicada no CLIENTE.md)
- Esse slide usa a imagem do profissional como fundo total do card (sem split)

---

### Fase 4 — Visual (HTML → PNG)

> ⚠️ Requer Playwright. Verificar com: `npx playwright --version`
> Se não instalado: `npx playwright install chromium`

**Formato:** 1080×1350px, inline CSS, Google Fonts como única dependência externa.

#### Formato 1 — Split imagem + texto

Cada slide é dividido em duas metades: uma com a imagem (sem overlay), outra com o texto.

**Divisão:**
- **Horizontal (esquerda/direita):** imagem ocupa metade lateral do card. Preferir quando a imagem é vertical ou quadrada e o texto é médio
- **Vertical (cima/baixo):** imagem ocupa metade superior ou inferior. Preferir quando a imagem é panorâmica ou o texto é extenso

**Variação obrigatória de posição da imagem entre slides:**
- Não repetir o mesmo lado em slides consecutivos
- Alternar: imagem à esquerda → direita → cima → baixo, conforme o layout e a imagem disponível
- O carrossel deve ter fluidez visual — a sequência de posições deve parecer intencional, não aleatória

**Regras visuais:**
- Imagem ocupa exatamente 50% do card, sem overlay, sem gradiente sobre ela
- Fundo do lado do texto: cor da identidade visual do cliente
- Tipografia: fontes definidas no CLIENTE.md
- Pode destacar palavras ou expressões com fonte diferente (bold, itálico, tamanho maior) ou cor diferente — sempre dentro da identidade visual do cliente
- Logo do cliente no rodapé de todos os slides
- Se o cliente for médico, dentista ou outro profissional regulado: incluir o texto legal no rodapé do lado do texto (fonte pequena, cor discreta — extrair do CLIENTE.md)

**Último slide (CTA de agendamento):**
- Imagem do profissional como fundo total do card (sem split, sem overlay escuro que prejudique a foto)
- Texto do CTA sobreposto, organizado e alinhado harmoniosamente para garantir boa leitura
- Usar caixa de texto com fundo semitransparente se necessário para legibilidade
- Logo no rodapé

**Processo:**
1. Criar todos os HTMLs
2. Salvar em `CLIENTE_[nome]/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/instagram/`
3. Renderizar slide 1 primeiro:
   ```bash
   npx playwright screenshot --viewport-size=1080,1350 --full-page "file:///[caminho-absoluto]/slide-01.html" "slide-01.png"
   ```

**CHECKPOINT:** mostrar slide 1 renderizado. Se aprovado, renderizar os demais.

4. Renderizar slides restantes e salvar PNGs na mesma pasta.

---

### Fase 5 — Versão TikTok (opcional)

Após slides de Instagram aprovados, perguntar:
> "Quer adaptar para TikTok também? (1080×1920, formato vertical)"

Se sim:
- Duplicar HTMLs para `tiktok/`
- Adaptar: `height: 1920px`, padding vertical mínimo 120px topo e base, fonte de corpo +15%
- Reposicionar elementos que ficarem mal distribuídos no vertical
- Renderizar:
  ```bash
  npx playwright screenshot --viewport-size=1080,1920 --full-page "file:///[caminho-absoluto]/slide-XX.html" "slide-XX.png"
  ```
- Mostrar slide 1 do TikTok antes de renderizar os demais

---

### Fase 6 — Checagem e output

Antes de entregar, verificar:
- [ ] Compliance: sem promessa de resultado, sem superlativo, sem comparação
- [ ] Disclaimer no rodapé (quando obrigatório para o cliente)
- [ ] Logo presente em todos os slides
- [ ] Variação de posição da imagem entre slides

Salvar `carousel-text.md` em `CLIENTE_[nome]/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/` com:
- Copy de todos os slides
- Imagens usadas por slide
- Posições de layout utilizadas (para referência na próxima peça)

---

## Output

```
CLIENTE_[nome]/conteudo/estaticos/carrosseis/[tema-YYYYMMDD]/
  carousel-text.md
  instagram/
    slide-01.html → slide-01.png
    ...
  tiktok/ (se solicitado)
    slide-01.html → slide-01.png
    ...
```

---

## Regras

- Sempre identificar o cliente antes de qualquer ação
- Copy vem pronta — não reescrever sem pedido explícito
- Pedir orientação de imagem se não conseguir interpretar os arquivos
- Variar posição da imagem entre slides — obrigatório
- Texto aprovado não muda na Fase 4
- Mostrar slide 1 antes de renderizar os demais
- Ajuste no visual → editar só o HTML alterado e re-renderizar apenas esse slide
- Tom de voz segue o cliente, não a BrainWave
