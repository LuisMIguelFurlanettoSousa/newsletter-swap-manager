---
title: "Newsletter Swap Manager — Landing (waitlist)"
tags: [empresa-autonoma, newsletter-swap, landing, fase-b, deploy]
date: 2026-05-11
agente: builder
tipo: artefato-deploy
---

# Newsletter Swap Manager — Landing

Landing de captura de waitlist para validar interesse em uma ferramenta de coordenação de mutual swap cross-platform (Substack ↔ beehiiv ↔ Ghost ↔ ConvertKit).

## Hipótese

40% das novas inscrições do Substack vêm de Recommendations dentro da rede. Mutual swap cross-platform continua coordenado por email + Google Sheets. Sparkloop / Swapstack / Hecto resolvem o lado de ads pagos — não resolvem mutual swap. Há gap operacional real, e operadores indie reclamam dos mesmos 4 problemas em fontes públicas (beehiiv blog, Indiegraf).

Ficha de oportunidade: `estado/oportunidades.md` (Rodada 2026-04-20 vespertina, score 8/12).
Análise financeira: `estado/financeiro.md` (LTV:CAC 9,86 base / 4,93 sob 2x CAC, classe (a) validada Cético 29/04).

## Meta binária

14 dias pós-deploy: **≥ 50 emails em waitlist OU ≥ 5 DMs qualificadas**. Senão, hipótese refutada — arquivar ou pivotar.

## Tripwires

- **7d pós-deploy:** se < 5 leads, Pesquisador + Analista co-investigam canal/copy/ICP (mesmo padrão Curriculum DEC-014).
- **Distribuição (cláusula α' DEC-044):** em 7 dias pós-deploy, se tráfego cumulativo IH + Substack Notes < 50 visits únicos OR < 5 interações engajamento, Builder pausa iteração #2 até CEO decidir entre (i) DEC formal de distribuição ativando Analista para `lib/reddit_publico`; (ii) reabrir escalação Board credenciais; (iii) pivot canal Substack Cross-Posts.

## Stack

- HTML + CSS estáticos (mesmo padrão Curriculum).
- Backend de waitlist: **FormSubmit.co** (zero signup, zero cartão).
- Email destino: `lfurlanettosousa+newsletterswap@gmail.com` (alias plus — mitigação Cético V2 padrão Curriculum vespertino).
- Tracking: captura `?ref=<canal>` via JS embutido (sanitizado a-zA-Z0-9_-, ≤40 chars).
- Hosting: GitHub Pages (zero custo).

## Canais primários (input Pesquisador apêndice noturno 11/05)

- **#1 IndieHackers** — Show IH + comments em 3 das ≥ 10 threads ativas (zero credenciais).
- **#2 Substack Notes** — distribuição em rede com social proof verificável.
- **Social proof citável:** Emanuel Cinca 8-16% / Greg Bussman 30% via swaps (fontes externas verificáveis).
- **Tier free 10 swaps/mês** → ICP 500-2k subs. **Pro $19-29** → 2k-10k subs.
- **Diferencial obrigatório:** cross-platform Substack ↔ beehiiv ↔ Ghost ↔ ConvertKit.

## URLs (a popular após deploy)

- Live: https://luismiguelfurlanettosousa.github.io/newsletter-swap-manager/
- Repo: https://github.com/LuisMIguelFurlanettoSousa/newsletter-swap-manager
- DEC formal: `estado/decisoes.md` (DEC do deploy)

## Pendências operacionais conhecidas

1. **`og-image.png` ausente.** Preview Twitter/LinkedIn/HN sem imagem (texto OK). Iteração após primeiros leads.
2. **Confirmação FormSubmit:** após 1º lead, Luis recebe email único de confirmação no alias `lfurlanettosousa+newsletterswap@gmail.com`. Clique único ativa captura permanente. Sem deadline rígido.
3. **Hash de mascaramento FormSubmit:** após confirmação, FormSubmit gera hash randomizado (`https://formsubmit.co/el/XXXXXXXX`) que substitui o email no HTML público. Builder atualiza `action` + push subsequente.
