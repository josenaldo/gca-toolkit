---
title: "<% tp.file.title %>"
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
type: lesson
mentora: Thaís Vieira
programa: Global Career Architecture (GCA)
sessao: <% tp.file.cursor(1) %>
week: <% tp.file.cursor(2) %>
cycle: <% tp.file.cursor(3) %>
interview_phase: "<% tp.file.cursor(4) %>"
status: seedling
tags:
  - inglês
  - entrevista
  - mentoria/gca
  - <% tp.file.cursor(5) %>
publish: false
material: "<% await tp.system.prompt('Nome do PDF da Session (com extensão)') %>"
---

# <% tp.file.title %>

> [!info] Sobre a aula
> Sessão **<% tp.file.title %>** do programa **Global Career Architecture (GCA)** com [Thaís Vieira](https://www.linkedin.com/in/thaisvieira-me).
> **Tema:** <% tp.file.cursor(6) %>
> **Fase do funil:** <% tp.file.cursor(7) %>
> **Ciclo:** <% tp.file.cursor(8) %>
> **Objetivo macro:** <% tp.file.cursor(9) %>

## Sumário

<% tp.file.cursor(10) %>

---

<% tp.file.cursor(11) %>

---

## War Room — Próximos Exercícios

> [!todo] Tarefa de execução (até a próxima sessão)
> <% tp.file.cursor(12) %>

<% tp.file.cursor(13) %>

---

## War Room — Histórias

> [!abstract] Banco de histórias / rascunhos
> Espaço para acumular histórias estruturadas, rascunhos de respostas e variações que emergem ao longo da sessão. Conteúdo em **inglês** quando for material de entrevista.

<% tp.file.cursor(14) %>

---

## Veja também

- [[00-Meta/templates/GCA/Roadmap]] — MOC mestre do programa
- [[<% tp.file.title %> - Workbook]] — exercícios e respostas desta sessão
- [[Mock Interview <% tp.file.cursor(2) %>]] — Mock Interview da mesma semana
- <% tp.file.cursor(15) %>
- [[Minha Narrativa Profissional]]
- [[Behavioral Questions]]
- [[STAR Method]]

## Material de referência

- 📄 PDF da aula: na pasta `03-Domínios/Inglês/GCA/Sessions/`
- 🌐 [LinkedIn da Thaís Vieira](https://www.linkedin.com/in/thaisvieira-me)
