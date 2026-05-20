---
name: transcrever-site
description: >
  Transcreve sites e landing pages a partir de uma URL.
  Mapeia a página principal, pergunta quais subpáginas (nível 1) incluir,
  e se houver níveis mais profundos derivados das selecionadas, pergunta antes de ir.
  Entrega: transcrição organizada em Markdown ou Google Doc, pronta pra análise de copy, SEO ou briefing.
  Use: "transcreve esse site", "quero mapear esse site", "transcreve a landing page", /transcrever-site.
---

# /transcrever-site — Transcrição de Sites e Landing Pages

## Para que serve
- Análise de concorrentes (posicionamento, copy, estrutura)
- Briefing de novo cliente (entender o que já existe antes de começar)
- Revisão de copy para melhorias de SEO (auditar o que está publicado)

---

## Workflow

### Fase 1 — Receber a URL e contexto

Ao iniciar, perguntar (se não vier junto com o comando):

1. **Qual a URL do site?**
2. **Qual o objetivo?**
   - Análise de concorrente
   - Briefing de cliente
   - Revisão de copy/SEO
   - Outro (pedir descrição)
3. **Onde quer receber a transcrição?**
   - Google Doc (criado automaticamente via Google Drive MCP)
   - Arquivo .md salvo localmente (pasta do cliente ou outra indicada)
   - Só exibir na tela

Usar o objetivo pra calibrar como organizar e apresentar a transcrição.

---

### Fase 2 — Transcrever a página principal

Usar `WebFetch` na URL fornecida.

Extrair e organizar:
- **Título da página** (tag `<title>` ou H1 principal)
- **Meta description** (quando visível na fonte)
- **Seções em ordem** — cada bloco com seu H2/H3 como título, seguido do texto
- **CTAs** — destacar chamadas pra ação com o label `[CTA]`
- **Links internos encontrados** — listar ao final como "Subpáginas encontradas"

Formato da transcrição da página principal:

```
# [Nome do site / Página principal]
URL: [url]

## Meta
- Título: ...
- Description: ...

## Conteúdo
### [Nome da seção]
[texto transcrito]

[CTA] "Texto do botão" → /destino

---
```

---

### Fase 3 — Apresentar subpáginas encontradas e perguntar

Após transcrever a página principal, listar todas as URLs internas encontradas (mesmo domínio, excluir: política de privacidade, termos, admin, login).

Perguntar:

> "Encontrei essas subpáginas no site. Quais você quer que eu transcreva?"
> - [ ] Todas
> - [ ] Nenhuma (só a principal já está bom)
> - [ ] Escolher: [lista numerada das subpáginas encontradas]

Aguardar resposta antes de continuar.

---

### Fase 4 — Transcrever subpáginas selecionadas (nível 1)

Para cada URL selecionada, repetir o mesmo processo da Fase 2.

Ao final de cada subpágina, verificar se ela tem links internos que ainda não foram transcritos (nível 2). Se sim:

> "A página [nome] tem links que ainda não transcrevemos: [lista]. Quer incluir algum?"
> - [ ] Sim, todos
> - [ ] Não
> - [ ] Escolher: [lista numerada]

Só perguntar sobre nível 2 se ele derivar de uma página que o usuário efetivamente escolheu no nível 1.

---

### Fase 5 — Consolidar e entregar

Montar um único documento com todas as páginas transcritas, nesta ordem:
1. Página principal
2. Subpáginas nível 1 (na ordem selecionada)
3. Subpáginas nível 2 (agrupadas sob a página pai)

Cabeçalho do documento:
```
# Transcrição: [Nome do site]
Transcrito em: [data]
Objetivo: [análise de concorrente / briefing / SEO]
URL base: [url]
```

**Se a entrega for Google Doc:**
- Usar `mcp__claude_ai_Google_Drive__create_file` para criar o arquivo
- Nome sugerido: `Transcrição — [nome do domínio] — [data]`
- Perguntar se quer salvar numa pasta específica do Drive (pedir o nome ou link da pasta); se não, criar na raiz
- Ao final, informar o link do doc criado

**Se a entrega for arquivo .md:**
- Perguntar onde salvar (se for cliente conhecido, sugerir `CLIENTE_[Nome]/conhecimento/transcricao-site-[dominio]-[data].md`)
- Salvar com `Write`

**Se for só na tela:**
- Exibir o conteúdo completo na conversa

---

## Regras de transcrição

- Transcrever o texto como está, sem reescrever ou resumir — o objetivo é fidelidade
- Se o objetivo for **revisão de SEO**, adicionar ao final de cada página um bloco `## Observações SEO` com: densidade de palavras-chave percebida, ausência de H1/H2, CTAs fracos, texto muito curto por seção
- Não incluir scripts, código, menus de navegação repetitivos ou rodapés genéricos
- Se o site bloquear o fetch (paywall, login, Cloudflare), informar e perguntar se quer tentar outra abordagem (ex: copiar e colar o HTML manualmente)
- Registrar data da transcrição no cabeçalho do documento: `Transcrito em: [data]`
