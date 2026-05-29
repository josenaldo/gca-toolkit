---
title: "<% tp.file.title %>"
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
type: community-session
mentora: Thaís Vieira
programa: Global Career Architecture (GCA)
community_session: <% tp.file.cursor(1) %>
theme: "<% tp.file.cursor(2) %>"
session_date: <% tp.file.cursor(3) %>
rounds_count: <% tp.file.cursor(4) %>
status: seedling
tags:
  - inglês
  - entrevista
  - mentoria/gca
  - community
  - role-play
  - <% tp.file.cursor(5) %>
publish: false
material: "<% await tp.system.prompt('Nome do PDF da Community session (com extensão)') %>"
---

# <% tp.file.title %>

> [!info] Sobre a sessão
> **Community Session** do programa **Global Career Architecture (GCA)** com [Thaís Vieira](https://www.linkedin.com/in/thaisvieira-me).
> Sessão em grupo (quinta à noite) com role-plays em pares (Breakout Rooms).
> **Data:** <% tp.file.cursor(3) %>
> **Tema central:** <% tp.file.cursor(2) %>
> **Executive mindset / propósito:** <% tp.file.cursor(6) %>

> [!quote] Seus rooms nesta sessão
> Lista dos rounds em que você (Josenaldo) participou ativamente, com sua role e o par:
> <% tp.file.cursor(7) %>

## Sumário

<% tp.file.cursor(8) %>

---

<% tp.file.cursor(9) %>

---

## Mentor Notes & Observações Globais

> [!warning] Notas da mentora pra todo o grupo
> <% tp.file.cursor(10) %>

---

<% tp.file.cursor(11) %>

---

## Veja também

- [[00-Meta/templates/GCA/Roadmap]] — MOC mestre do programa
- [[<% tp.file.title %> - Workbook]] — notas pós-exercício e vocabulário aprendido
- <% tp.file.cursor(12) %>
- [[STAR Method]]
- [[Behavioral Questions]]
- [[Minha Narrativa Profissional]]

## Material de referência

- 📄 PDF da sessão: na pasta `03-Domínios/Inglês/GCA/Community/`
- 🌐 [LinkedIn da Thaís Vieira](https://www.linkedin.com/in/thaisvieira-me)
