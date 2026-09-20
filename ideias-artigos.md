# Pipeline de artigos — tiofih.github.io

Rascunho de ideias levantadas dos projetos e memórias da máquina.
Este arquivo **não** é publicado (não tem front-matter). Sirva-se dele para decidir o que entra.

## Como usar

- **`[ ]`** = candidato a publicar (você decide).
- **`[x]`** = decidiu incluir. Ao publicar, vire-o em um post em `_posts/` e feche a linha.
- Cada ideia tem **material-fonte** (caminho real no disco) para puxar o conteúdo sem caçar.

---

## Prioridade / assinatura (temas que quase não existem publicados)

- [ ] **1. SDD — Desenvolvimento dirigido a especificação com IA**
  - Ângulo: metodologia spec-first em sessões numeradas: refinamento → TDD estrito → revisor → validação. 69 sessões com rastreabilidade requisito → commit. Um "como eu programo com agente de IA" muito concreto.
  - Fonte: `poke-htmx/sdd/PROTOCOL.md`, `poke-htmx/sessions/` (0001–0069), `poke-htmx/SESSIONS.md`
  - Esforço: alto · Tipo: tutorial/metodologia

- [ ] **2. O custo dos tokens: MCP vs grep (pedra no zap fundo)**
  - Ângulo: seu `AGENTS.md` já tem um comparativo **medido** (bytes/tokens por ferramenta: CBM Scout vs grep brute, ruby-mcp, graphify). Benchmarkar a própria toolchain é tema raríssimo.
  - Fonte: `/Users/tiofih/workspace/AGENTS.md` (seção "Diretrizes de uso de tokens"), sessão `16c476bb`
  - Esforço: médio · Tipo: análise/benchmark

- [ ] **3. Por que server-rendered + HTMX venceu o React (no meu side project)**
  - Ângulo: a tese anti-SPA com prova de fogo — batalhas Pokémon server-rendered, sem framework JS no front.
  - Fonte: `poke-htmx/` + `poke-htmx/draft-arquitetura-design-patterns.md` + gotcha `htmx-nao-troca-em-nao-2xx.md`
  - Esforço: médio · Tipo: opinião/case

## Case studies (build logs)

- [ ] **Conway em Godot 4 — TDD desde o 1º commit**
  - Ângulo: 20 relatórios de teste (gdUnit4), regras B3/S23, padrões (Glider, Gosper), RLE, regras alternativas, toro.
  - Fonte: `game-of-life/README.md`, `game-of-life/reports/`, `game-of-life/tests/unit/`
  - Esforço: médio

- [ ] **Design de um idle game — o GDD do Love Clicker**
  - Ângulo: core loop, prestige, crescimento de custo, vocabulário de jogo. "O chato bem-feito" de game design.
  - Fonte: `love-clicker/GDD.md`, `love-clicker/REQUIREMENTS.md`
  - Esforço: médio

- [ ] **Fazendo um mod de Terraria em C# (tModLoader)**
  - Ângulo: onboarding real do zero, incluindo as dores de toolchain/LSP que ficaram na memória.
  - Fonte: `terraria-mod/doppelganger/`, sessões da memória sobre tmodloader/LSP
  - Esforço: médio

- [ ] **Poke-HTMX: o motor de auto-battler**
  - Ângulo: efetividade de tipos, PP/golpes, motor de batalha, pool de oponentes — o design por trás do game loop.
  - Fonte: `poke-htmx/draft-auto-battler.md`, `poke-htmx/sessions/0009`–`0016`, `draft-arquitetura-design-patterns.md`
  - Esforço: alto

## Posts técnicos curtos (gotchas — ótimos para engajamento)

- [ ] **htmx não faz swap em resposta 4xx** — e o padrão "200 + fragmento amigável". Fonte: `poke-htmx/gotchas/htmx-nao-troca-em-nao-2xx.md`
- [ ] **Sass `@extend placeholder not found`** no Jekyll — `poke-htmx/gotchas/sass-extend-placeholder-not-found.md`
- [ ] **Jekyll build quebra com bundler 1.17.3 no Ruby 3.4+** — `poke-htmx/gotchas/jekyll-ruby-3-4-bundler-pin.md`
- [ ] **Cache da PokéAPI** (gateway + cache) — `poke-htmx/sessions/0021`/`0022`
- [ ] **Remoção semântica em vez de delete** — `poke-htmx/sessions/0002`
- [ ] **Paginação/filtro na listagem + responsividade mobile** — `poke-htmx/sessions/0006`, `playtest-02-responsividade.md`

## Off-topic (interesses pessoais)

- [ ] **Guia: descarboxilação e manteiga infundida** — `vaults/main/receitas/descarboxilacao.md`, `manteiga-infusionada.md`
  - Tipo: guia prático, nicho + voz pessoal. Bem diferente do resto — pode virar um canal paralelo.

---

## Mecânica de publicação (estado atual, rev. 2026-09-20)

- `tiofih.github.io` é o **folio** Jekyll: coleção `_portfolio`, páginas (`sobre`, `portfolio`, `artigos`).
- O blog real é o repo **`tiofih/blog`** (tema minima): posts em `_posts/YYYY-MM-DD-slug.md`, servido como project site em `tiofih.github.io/blog/`.
- Para publicar artigo novo: criar o post em `blog/_posts/`, commitar + push no repo `blog`, e adicionar a linha correspondente em `tiofih.github.io/artigos.md` (é o que põe o post no header via página `artigos`).
- Build local do folio: `bundle exec jekyll build` (lockfile modernizado em 2026-09-20: bundler 4.0.11, jekyll 4 + sass-embedded; o pin `bundler 1.17.3` quebrava no Ruby 3.4).
- Gotchas de build já documentados: `sass-extend-placeholder-not-found.md` e `jekyll-ruby-3-4-bundler-pin.md`.
