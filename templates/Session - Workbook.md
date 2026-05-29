---
title: "<% tp.file.title %>"
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
type: lesson-workbook
mentora: Thaís Vieira
programa: Global Career Architecture (GCA)
sessao: <% tp.file.cursor(1) %>
week: <% tp.file.cursor(2) %>
cycle: <% tp.file.cursor(3) %>
status: seedling
tags:
  - inglês
  - entrevista
  - mentoria/gca
  - workbook
publish: false
---

# <% tp.file.title %>

> [!info] Sobre este documento
> Working document para fazer os exercícios e responder os prompts da [[<% tp.file.cursor(4) %>]].
> Cada exercício traz: **regra GSC associada**, **armadilhas a evitar** (se houver feedback prévio), e **slot de resposta vazio** pra você preencher.
> Conteúdo das respostas em **inglês** quando for material de entrevista (pitch, STAR, etc.); contexto e raciocínio podem ser em PT-BR.

> [!todo] Protocolo de execução
>
> 1. Resolver os exercícios sem usar IA pra escrever a resposta — você é quem escreve.
> 2. Quando travar, invocar `/coaching` (modo socrático estrito — guia, nunca escreve por você).
> 3. Revisar contra as **Regras invioláveis** abaixo antes de fechar cada slot.
> 4. Voltar ao Workbook periodicamente — refinar o que rascunhou (este é documento vivo).

> [!warning] Regras invioláveis (transversais a todas as Sessions)
>
> - **BLUF** — Bottom Line Up Front. Comece pela conclusão.
> - **Silêncio > filler.** Quando falar em voz alta: pausar 2-3s em vez de "é é é", "so so", "in in".
> - **"I" não "We".** Você está vendendo sua execução.
> - **Power Verbs** ativos: Orchestrated, Spearheaded, Leveraged, Mitigated, Overhauled, Streamlined, Architected, Engineered.
> - **Show, don't tell.** Não diga que é confiável — **demonstre** via síntese, autoridade e outcome.
> - **Zero narrativa de guerreiro/batalhador.** Senioridade é o oposto de sacrifício.
> - **Time-box rígido** quando aplicável (PPF ≤ 90s, STAR ≤ 2min).

## Sumário

<% tp.file.cursor(5) %>

---

<% tp.file.cursor(6) %>

---

## Veja também

- [[00-Meta/templates/GCA/Roadmap]] — MOC mestre do programa
- [[<% tp.file.cursor(4) %>]] — Session processada (frameworks, glossário, exemplos)
- [[Mock Interview <% tp.file.cursor(2) %>]] — Mock Interview da mesma semana
- [[Minha Narrativa Profissional]]
- [[STAR Method]]
