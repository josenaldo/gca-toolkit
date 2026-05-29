---
title: "<% tp.file.title %>"
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
type: mock-interview-script
mentora: Thaís Vieira
programa: Global Career Architecture (GCA)
sessao: "mock-<% tp.file.cursor(1) %>"
week: <% tp.file.cursor(2) %>
cycle: <% tp.file.cursor(3) %>
mock_type: "<% tp.file.cursor(4) %>"
duration_min: <% tp.file.cursor(5) %>
persona: "<% tp.file.cursor(6) %>"
status: seedling
tags:
  - inglês
  - entrevista
  - mentoria/gca
  - mock-interview
  - script
publish: false
---

# <% tp.file.title %>

> [!info] Sobre este documento
> Working document para rascunhar, afinar e memorizar as respostas das perguntas da [[<% tp.file.cursor(7) %>]].
> Cada pergunta tem: **regra GSC**, **armadilhas a evitar** (extraídas do feedback da Thaís), e **slots de rascunho** em EN.
> Conteúdo em **inglês** — é o que vai ser falado em entrevista.

> [!quote] Persona e formato deste mock
> **Persona simulada:** <% tp.file.cursor(8) %>
> **Tipo:** <% tp.file.cursor(9) %>
> **Duração:** <% tp.file.cursor(10) %> minutos
> **Foco / regra de estresse:** <% tp.file.cursor(11) %>

> [!todo] Protocolo de execução
>
> 1. Rascunhar em EN dentro do slot "Draft".
> 2. Time-box: **máximo 90s (Q1 — PPF) ou 2min (demais)**.
> 3. Ler em voz alta com cronômetro.
> 4. Revisar: cortar gordura, trocar fillers por pausas, substituir verbos fracos por Power Verbs.
> 5. Memorizar **tópicos**, não frases.
> 6. Gravar áudio para auto-crítica antes da próxima sessão.

> [!warning] Regras invioláveis (do feedback da Thaís)
>
> - **BLUF** — Bottom Line Up Front. Comece pela conclusão.
> - **Silêncio > filler.** Se travar, pausar 2-3s. Nunca "é é é", "so so", "in in".
> - **"I" não "We".** Você está vendendo sua execução.
> - **Power Verbs** ativos: Orchestrated, Spearheaded, Leveraged, Mitigated, Overhauled, Streamlined, Architected, Engineered.
> - **Show, don't tell.** Não diga que é confiável — **demonstre** via síntese, autoridade e outcome.
> - **Zero narrativa de guerreiro/batalhador.** Senioridade é o oposto de sacrifício.
> - **Time-box rígido.** Q1 ≤ 90s. Demais ≤ 2min.

## Sumário

<% tp.file.cursor(12) %>

---

<% tp.file.cursor(13) %>

---

## Veja também

- [[00-Meta/templates/GCA/Roadmap]] — MOC mestre do programa
- [[<% tp.file.cursor(7) %>]] — feedback consolidado desta mock
- [[Session <% tp.file.cursor(2) %>]] — Strategic Session da mesma semana
- [[STAR Method]]
- [[Behavioral Questions]]
- [[Minha Narrativa Profissional]]
