---
title: "URLs distribuídas com ?ref= por canal — Newsletter Swap Manager"
tags: [empresa-autonoma, tracking, distribution, newsletter-swap]
date: 2026-05-12
agente: builder
tipo: referencia
---

# URLs canônicas por canal externo

> Tracking pareado ao Curriculum (commit 7d5681d daquele repo). Toda URL distribuída
> em canal externo DEVE usar a forma canônica abaixo. O `?ref=<canal>` é capturado pelo JS
> da landing (regex `^[a-zA-Z0-9_-]{1,40}$`) e enviado como hidden field no FormSubmit —
> cada lead chega na inbox do Luis (`lfurlanettosousa+newsletterswap@gmail.com`) com `ref` declarado.

**Base URL:** `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/`

## Prioridade de canais (sob AO-2026-05-12-004 — Board 2026-05-12 06:46)

1. **IndieHackers** — canal PRIMÁRIO. Pesquisador validou via WebSearch ≥ 10 threads ativas, ICP exato (newsletter writers / indie publishers), signup sem cartão, zero problema de conta nova. Distribuidor rascunhar 3 comments substantivos antes da próxima rodada matinal.
2. **Substack Notes** — canal SECUNDÁRIO. Audience nativa do ICP (NS writers já estão na plataforma). Sem credencial bloqueante.
3. **Reddit r/Substack + r/Newsletters** — em fila para D+3/D+4 pós account warming `the_dev_founder` (conta criada 10/05, sob bloqueio AO-2026-05-12-004 enquanto karma < 50 ou < 7d). Rascunhos Distribuidor de 11/05 ainda válidos; só publicação está gated.
4. **Demais (LinkedIn, HN, etc.)** — oportunísticos, sem ordem rígida.

## Tabela canônica

| Canal | URL canônica | Status / Notas |
|---|---|---|
| IndieHackers (PRIMÁRIO) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=ih` | Mandato Distribuidor próxima rodada matinal — 3 comments. |
| IndieHackers (post original próprio) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=ih-post` | Quando Distribuidor publicar post Show IH (não rascunhado ainda). |
| Substack Notes (SECUNDÁRIO) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=substack-notes` | Audience nativa do ICP. |
| Substack (post de outro newsletter cross-post) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=substack-crosspost` | Para quando NS writers compartilharem espontaneamente. |
| Reddit r/Substack | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=reddit-substack` | Bloqueado AO-2026-05-12-004 até karma `the_dev_founder` ≥ 50 ou D+7. |
| Reddit r/Newsletters | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=reddit-newsletters` | Hoje (12/05) Board autorizou 1 post de teste — Rascunho 2 do Distribuidor (thread 1t45tk0). Se passar shadowban check 12h → escalar D+1. |
| Reddit r/SubstackWriters | banido — não distribuir | `lib/reddit_publico.status_subreddit` retornou `banido` em 28/04 (precedente Pesquisador). |
| Twitter / X (post orgânico) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=twitter` | Bloqueado por credenciais (`pendente-fef52521`). |
| Twitter / X (DMs writers-âncora) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=twitter-dm` | Bloqueado por credenciais. |
| LinkedIn (post orgânico) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=linkedin` | Luis tem conta — pode postar em pt-br ou en. |
| Hacker News (Show HN) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=hn` | Conta no HN sem cartão. |
| Lobste.rs | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=lobsters` | Read-only sem invite — apenas se invite materializar. |
| dev.to | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=devto` | OAuth GitHub que já temos. Audience menos exata (devs > writers) mas válido pra cross-pollinate. |
| Medium pessoal | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=medium` | Sem cartão. |
| Hashnode | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=hashnode` | Sem cartão. Audience marginal pro ICP NS. |
| Email outbound (DMs personalizados) | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/?ref=outbound-email` | Genérico — Luis pode acrescentar `&id=<nome>` localmente. |
| Direct / desconhecido | `https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/` | Sem `?ref=` → JS preenche hidden field com `direct`. |

## Como o tracking funciona (sem analytics externo)

1. Visitante abre URL com `?ref=ih`.
2. JS pequeno (linhas finais do `index.html`) lê `URLSearchParams`, valida regex `^[a-zA-Z0-9_-]{1,40}$` (anti-injeção), preenche `<input id="ref-source" hidden>`.
3. Visitante submete waitlist → FormSubmit envia email pra `lfurlanettosousa+newsletterswap@gmail.com` com `email`, `pain`, `current_workflow`, `platforms`, `ref` em tabela.
4. Luis lê: cada lead chega com canal de origem declarado, possibilita atribuição rudimentar de canal.
5. Builder mantém esta tabela atualizada conforme novos canais entram.

## Tripwires de uso

- **Canal sem `?ref=` por 2 rodadas consecutivas (DEC-044 herança Curriculum):** CEO abre DEC formal de incidente. Use a tabela acima como gabarito antes de qualquer compartilhamento.
- **Tripwire α' DEC-044 (NS-específico):** em 2026-05-18 se IH + Substack Notes < 50 visits OR < 5 interações → Builder pausa iteração #2 até CEO decidir distribuição.
- **Tripwire 7d (NS):** < 5 leads até 2026-05-18 → Pesquisador + Analista co-investigam canal/copy/ICP.

## Pareamento Curriculum

Esta tabela espelha estruturalmente o `DISTRIBUTION_URLS.md` do Curriculum Planning (commit 7d5681d). Padrão validado e reusado conforme CLAUDE.md regra 17 (bundle reproduzível por vertical). Diferenças materiais:

- **Ordem de prioridade**: NS lista IH primeiro (validado pelo Pesquisador 15:00 + Board AO-2026-05-12-004); Curriculum lista canais sem priorização explícita.
- **Reddit posting**: NS tem r/SubstackWriters banido (precedente 28/04); Curriculum tem r/onlinecoursecreators banido (precedente 28/04). Padrão: revalidar via `lib/reddit_publico.status_subreddit` antes de qualquer rascunho que cite sub.
- **Status em fila**: NS Reddit em fila D+3/D+4 sob AO-2026-05-12-004; Curriculum sem bloqueio explícito atual.

## Plausible community (iteração #2 futura, herança Curriculum)

Plausible community continua planejada como camada adicional de analytics quando waitlists materializarem. Esta tabela complementa, não substitui. Sem urgência operacional.
