# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

# BrainWave — Claude Code OS

## O que é esse workspace
Workspace operacional da BrainWave. Aqui organizamos a operação da agência, produzimos conteúdo para clientes e desenvolvemos a estratégia e comunicação própria da BrainWave.

**Estrutura de pastas:**
- `CLIENTE_BrainWave/` — cliente interno da BrainWave (mesma estrutura dos clientes externos)
- `CLIENTE_Dr-Diler/`, `CLIENTE_Dra-Isabel-Carazzo/`, `CLIENTE_Dra-Janaina-Marchi/`, `CLIENTE_Roberta-Barni/` — pasta por cliente externo
- `clientes/_modelo-cliente/` — template base pra duplicar quando chegar novo cliente
- `propostas/` — propostas comerciais
- `dados/` — arquivos para análise (CSV, PDF, relatórios)
- `tarefas.md` — lista de tarefas corrente
- `_contexto/` — memória do sistema (não apagar)
- `templates/skills/` — templates de skills prontos pra personalizar com /mapear
- `templates/ferramentas/catalogo.md` — APIs e ferramentas disponíveis pra usar em skills

**Estrutura interna de cada cliente:**
```
[cliente]/
├── CLIENTE.md
├── skills/                        ← skills específicas do cliente
├── planejamento/                  ← planos mensais e calendários editoriais
├── comercial/
├── conhecimento/
│   └── identidade-visual/         ← diretrizes criativas, links de acervo, exemplos
├── conteudo/
│   ├── estaticos/
│   │   ├── carrosseis/
│   │   ├── cards/
│   │   └── capas/
│   │       ├── reels/
│   │       └── thumbnails/
│   ├── roteiros-curtos/           ← roteiros de reels e vídeos curtos
│   ├── youtube/
│   ├── blog/
│   └── google/
├── dados/
├── site/
└── trafego/
```

**Estrutura adicional exclusiva do CLIENTE_BrainWave:**
```
CLIENTE_BrainWave/
├── [mesma estrutura acima]
├── comercial/
│   └── propostas/
├── administrativo/
│   └── contratos/
└── operacional/
    ├── onboarding/
    └── processos/
```

## Sobre o negócio
A BrainWave é uma empresa de estratégia e desenvolvimento de marketing. O posicionamento é de braço estratégico das empresas — não uma agência de posts, mas quem detém a inteligência de negócio do cliente. Dois braços de serviço: (1) estratégia de marketing — diagnóstico de cenário e mercado + plano estratégico, vendido separado; (2) gestão recorrente mensal — execução do aprovado na estratégia, com peso em produção de conteúdo digital e, em alguns clientes, estratégias comerciais.

## O que fazemos aqui
- Diagnósticos e planos estratégicos de marketing
- Gestão de conteúdo para canais digitais de clientes (carrosséis, reels, YouTube)
- Estratégias e fluxos comerciais (ManyChat, Kommo CRM)
- Propostas comerciais
- Desenvolvimento da comunicação e estratégia própria da BrainWave

## Clientes e contexto
Atende clientes externos com equipe dedicada por cliente: designer, copywriter, editor de vídeo, gestora de projeto, gestor de tráfego (quando incluso) e Gabriella. Maioria dos clientes atuais é da área de saúde, sem restrição de nicho. A BrainWave é tratada como cliente interno — sua pasta (`CLIENTE_BrainWave/`) segue a mesma estrutura dos clientes externos. Cada cliente tem sua pasta na raiz do workspace com prefixo `CLIENTE_` e um `CLIENTE.md` que concentra o contexto específico daquele cliente.

Ao trabalhar num cliente específico, ler o `CLIENTE.md` da pasta dele antes de qualquer tarefa.

## Tom de voz
Coloquial mas profissional — conversa, sem gírias, sem ser totalmente informal. Transmite conhecimento, seriedade e posicionamento claro. A BrainWave tem valores definidos: marketing é o departamento mais importante de uma empresa, não só "fazer post de internet".

Evitar: qualquer coisa que soe escrito por IA, frases de contraste, travessão (—), palavras como "crucial", "mergulhe", "no mundo de hoje", "é essencial que".

## Ferramentas conectadas
- [ ] Notion (MCP disponível — ver link da base por cliente no CLIENTE.md de cada um)
- [x] Google (Drive, Docs, etc)
- [ ] Canva (MCP disponível)
- [x] Gmail (MCP instalado — ver acima)
- [x] Google Calendar (MCP instalado — usar SOMENTE a conta ffmkt.contato@gmail.com)
- [x] Gmail (MCP instalado — usar SOMENTE a conta ffmkt.contato@gmail.com — não conectar outras contas)
- Meta Ads (alguns clientes)
- Google Ads (alguns clientes)
- Opus (corte de lives)
- Google Flow

---

## Contexto do negócio

No início de toda conversa, ler os seguintes arquivos (se existirem e estiverem configurados):

1. `_contexto/empresa.md` — quem é o usuário, o que faz, como funciona o negócio
2. `_contexto/preferencias.md` — tom de voz, estilo de escrita, o que evitar
3. `_contexto/estrategia.md` — foco atual, prioridades, o que pode esperar

Se a conversa for sobre um cliente específico, ler também o `CLIENTE.md` da pasta daquele cliente.

Usar essas informações como base pra qualquer resposta ou decisão. Ao sugerir prioridades, formatos ou abordagens, considerar o foco atual descrito em `estrategia.md`.

Para qualquer tarefa visual (carrossel, proposta, slide, landing page), consultar `marca/design-guide.md` como referência de estilo — ou o arquivo de IV indicado no `CLIENTE.md` do cliente.

Não é necessário listar o que foi lido nem confirmar a leitura. Apenas usar o contexto naturalmente.

---

## Fluxo de trabalho

Antes de executar qualquer tarefa, verificar se existe uma skill relevante em `.claude/skills/` ou `.claude/commands/`.
Se encontrar, seguir as instruções da skill.
Se não encontrar, executar a tarefa normalmente.

Ao concluir uma tarefa que não tinha skill mas parece repetível (o usuário provavelmente vai pedir de novo no futuro), perguntar:

> "Isso pode virar uma skill pra próxima vez. Quer que eu crie?"

Não perguntar pra tarefas pontuais ou perguntas simples. Só quando o padrão de repetição for claro.

---

## Aprender com correções

Quando o usuário corrigir algo, melhorar uma resposta ou dar uma instrução que parece permanente (frases como "na verdade é assim", "não faça mais isso", "prefiro assim", "sempre que...", "evita...", "da próxima vez..."), perguntar:

> "Quer que eu salve isso pra não precisar repetir?"

Se sim, identificar onde faz mais sentido salvar:

- **Sobre o negócio** → `_contexto/empresa.md`
- **Sobre preferências e estilo** → `_contexto/preferencias.md`
- **Sobre prioridades e foco atual** → `_contexto/estrategia.md`
- **Sobre um cliente específico** → `clientes/[nome-cliente]/CLIENTE.md`
- **Regra de comportamento nessa pasta** → `CLAUDE.md`

Salvar com uma linha nova clara, sem reformatar o arquivo inteiro. Confirmar o que foi salvo mostrando a linha adicionada.

---

## Manter contexto atualizado

Ao terminar uma tarefa que mudou algo relevante no projeto (novo cliente, nova skill, mudança de foco, novo processo, ferramenta instalada, estrutura de pastas alterada), perguntar:

> "Isso mudou algo no teu contexto. Quer que eu atualize os arquivos de memória?"

Se sim, identificar o que precisa atualizar:

- **Novo cliente, serviço, ferramenta, equipe** → `_contexto/empresa.md`
- **Mudança de prioridade ou foco** → `_contexto/estrategia.md`
- **Correção de tom ou estilo** → `_contexto/preferencias.md`
- **Contexto específico de um cliente** → `clientes/[nome-cliente]/CLIENTE.md`
- **Nova pasta, regra de organização, skill criada** → `CLAUDE.md`
- **Mudança visual (cores, fontes, logo)** → `marca/design-guide.md`

Mostrar o que vai mudar antes de salvar. Não reformatar o arquivo inteiro, só adicionar ou editar a linha relevante.

**Quando NÃO perguntar:**
- Tarefas pontuais que não mudam o contexto (ex: escrever um email, criar um post avulso)
- Perguntas simples ou conversas sem ação
- Mudanças que já foram salvas pelo bloco "Aprender com correções"

---

## Criação de skills

Quando o usuário pedir pra criar uma nova skill:

1. Verificar se existe um template relevante em `templates/skills/`. Se existir, usar como base e adaptar pro contexto do usuário
2. Perguntar: "Essa skill é específica pra esse projeto ou vai ser útil em qualquer projeto?"
   - Específica desse negócio → salvar em `.claude/skills/nome-da-skill/SKILL.md` (local)
   - Útil em qualquer projeto → salvar em `~/.claude/skills/nome-da-skill/SKILL.md` (global)
3. Ler `_contexto/empresa.md` e `_contexto/preferencias.md` pra calibrar o conteúdo da skill ao contexto do negócio
4. Se a skill precisar de arquivos de apoio (templates, referências, exemplos), criar dentro da pasta da skill
5. Seguir o fluxo da skill-creator nativa do Claude Code
