---
title: "<% tp.file.title %>"
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
type: mock-interview
mentora: Thaís Vieira
programa: Global Career Architecture (GCA)
sessao: "mock-<% tp.file.cursor(1) %>"
week: <% tp.file.cursor(2) %>
cycle: <% tp.file.cursor(3) %>
interview_phase: "<% tp.file.cursor(4) %>"
mock_type: "<% tp.file.cursor(5) %>"
duration_min: <% tp.file.cursor(6) %>
persona: "<% tp.file.cursor(7) %>"
status: seedling
tags:
  - inglês
  - entrevista
  - mentoria/gca
  - mock-interview
  - feedback
publish: false
material: "<% await tp.system.prompt('Nome do PDF da Mock Interview (com extensão)') %>"
---

# <% tp.file.title %>

> [!info] Sobre a sessão
> **Mock Interview** do programa **Global Career Architecture (GCA)** com [Thaís Vieira](https://www.linkedin.com/in/thaisvieira-me).
> Simulação de entrevista — teste de postura técnica, uso de frameworks estruturados (**STAR / PPF / BLUF**) e redução de **latência vocal** e **over-explaining**.
> Esta nota consolida **as perguntas, as regras GSC e os comentários da Thaís**. O script de respostas fica em [[<% tp.file.title %> - Workbook]].

> [!quote] Persona e formato deste mock
> **Persona simulada:** <% tp.file.cursor(8) %>
> **Tipo:** <% tp.file.cursor(9) %>
> **Duração:** <% tp.file.cursor(10) %> minutos
> **Foco / regra de estresse:** <% tp.file.cursor(11) %>

## Sumário

<% tp.file.cursor(12) %>

---

<% tp.file.cursor(13) %>

---

## Diagnóstico — Padrões Recorrentes

> [!danger] Sintomas transversais identificados pela Thaís
> Os comentários se repetem em várias perguntas. Consolidando os eixos de falha:

<% tp.file.cursor(14) %>

---

## Plano de Ação — Próxima Mock

<% tp.file.cursor(15) %>

---

## Veja também

- [[00-Meta/templates/GCA/Roadmap]] — MOC mestre do programa
- [[<% tp.file.title %> - Workbook]] — script de respostas para esta mock
- <% tp.file.cursor(16) %>
- [[STAR Method]]
- [[Behavioral Questions]]
- [[Minha Narrativa Profissional]]

## Material de referência

- 📄 PDF da mock interview: na pasta `03-Domínios/Inglês/GCA/Mock Interview/`
- 🌐 [LinkedIn da Thaís Vieira](https://www.linkedin.com/in/thaisvieira-me)
