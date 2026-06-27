# GCA Toolkit — Skills do Claude Code para a mentoria Global Career Architecture

Um conjunto de **9 skills do Claude Code** + **9 templates do Obsidian** para transformar os PDFs da mentoria GCA (Strategic Sessions, Mock Interviews, Community Sessions e o Cronograma) em notas estruturadas, navegáveis e — o mais importante — em **workbooks de prática ativa** dentro de um vault Obsidian.

> Feito originalmente pro meu vault pessoal e compartilhado com a galera do GCA. **Você vai precisar adaptar alguns caminhos e nomes** — está tudo documentado na seção [Como adaptar](#como-adaptar).

---

## A ideia em 30 segundos

Cada material da mentoria vira **duas notas**:

1. **Processed** (camada de conhecimento) — o conteúdo do PDF estruturado: frameworks (PPF, STAR, BLUF), Power Verbs, glossários, mentor notes da Thaís, diagnóstico, plano de ação. É o que você **lê e consulta**.
2. **Workbook** (camada de prática) — um *scaffold* de exercícios com os slots de resposta **vazios**. É onde você **escreve com a sua própria mão**. As skills nunca preenchem por você.

E uma quinta skill, `coaching`, te acompanha em **modo socrático estrito** enquanto você preenche o Workbook: ela pergunta, aponta violações de regra com citação ao Processed, propõe alternativas em tabela — mas **nunca escreve a resposta por você**. O produto é a sua retenção, não o texto.

```
PDF da Thaís ──▶ /process-* ──▶ Processed.md (leitura)
                              └▶ Workbook.md  (prática) ──▶ /coaching (te guia)
```

---

## Pré-requisitos

| Ferramenta | Para quê | Obrigatório? |
|---|---|---|
| **Claude Code** | rodar as skills (`/process-session` etc.) | Sim |
| **Obsidian** | abrir e navegar o vault (wikilinks, callouts, Dataview) | Sim |
| **Plugin [Templater](https://github.com/SilentVoid13/Templater)** | os templates usam sintaxe `<% %>` | Recomendado* |

\* As skills resolvem os placeholders Templater (`<% tp.file.cursor(N) %>`) **na hora de gerar a nota** — a nota final é markdown puro, sem sintaxe Templater. O Templater só é necessário se você quiser criar notas manualmente a partir dos templates. Se você só usa as skills, pode dispensá-lo.

---

## O que tem no pacote

```
gca-toolkit/
├── README.md                  ← este arquivo
├── skills/                    ← copiar pra .claude/skills/ do seu projeto
│   ├── process-roadmap/SKILL.md
│   ├── process-session/SKILL.md
│   ├── process-mock-interview/SKILL.md
│   ├── process-community/SKILL.md
│   ├── coaching/SKILL.md
│   ├── processar-vaga/SKILL.md
│   ├── process-question/SKILL.md
│   ├── seed-question/SKILL.md
│   └── glosa-video/SKILL.md
└── templates/                 ← copiar pra 00-Meta/templates/GCA/ do seu vault
    ├── Roadmap.md
    ├── Session - Processed.md
    ├── Session - Workbook.md
    ├── Mock Interview - Processed.md
    ├── Mock Interview - Workbook.md
    ├── Community - Processed.md
    ├── Community - Workbook.md
    ├── Template - Vaga.md
    └── Template - Interview Question.md
```

### As 9 skills

| Skill | Comando | O que faz |
|---|---|---|
| **process-roadmap** | `/process-roadmap` | Lê o PDF do **Cronograma** e gera o `Roadmap.md` — o MOC mestre com as 12 semanas / 3 ciclos. Roda **uma vez** no início (e de novo só se a Thaís refinar o cronograma). É a **fonte de inferência** das outras skills (tema, persona, fase do funil). |
| **process-session** | `/process-session` | Lê um PDF de **Strategic Session** → gera `Session NN - <Nome>.md` (Processed) + `Workbook.md`. |
| **process-mock-interview** | `/process-mock-interview` | Lê um PDF de **Mock Interview** → gera Processed (perguntas Q1-Qn + mentor notes + diagnóstico) + Workbook (slots de draft por pergunta). |
| **process-community** | `/process-community` | Lê um PDF de **Community Session** (em grupo, com role-plays em Breakout Rooms) → gera Processed + Workbook reflexivo. Detecta automaticamente em quais *rooms* **você** participou. Não consulta o Roadmap (Community é stream paralelo). |
| **coaching** | `/coaching` | Modo socrático: te ajuda a refinar uma resposta no Workbook **sem nunca escrevê-la por você**. Verifica regras GSC (BLUF, Power Verbs, "I" não "We", time-box, etc.) e cita o Processed. |
| **processar-vaga** | `/processar-vaga <url>` | Transforma uma URL de vaga em **nota canônica de preparação** com 10 seções: diagnóstico da empresa, match analysis, pitch adaptado, prováveis perguntas em 6 fases, histórias do banco mapeadas, cheat sheet de vocabulário, logística e checklist. Lê o dossiê do candidato (Narrativa Profissional + Roadmap GCA) pra personalizar. |
| **process-question** | `/process-question Q###` | Expande uma semente do backlog de perguntas em **dois Q-files completos** (EN + PT): Standard Answer ~400-450 palavras em primeira pessoa (voice-note style), Alternative Questions, Answer Strategy, Checklist, Common Traps, Vocabulary e Delivery Notes. |
| **seed-question** | `/seed-question "<pergunta>"` | Adiciona uma nova semente ao backlog de perguntas sem expandir ainda. Infere `category`, `phase` e `angle` automaticamente, confirma antes de inserir, e mantém os contadores do backlog. |
| **glosa-video** | `/glosa-video <url>` | Cria fichamento ("Glosa") de vídeo do YouTube em `02-Glosas/<ano>-<slug>.md` — TL;DR, Pontos-chave, Momentos-chave com timestamps, Citações verbatim. Para vídeos de carreira/liderança/soft skills, também gera uma seção **Frases para entrevista** com 15-25 trechos diretamente reutilizáveis em respostas de entrevista. |

### Os 9 templates

Nove `.md` com placeholders Templater (`<% tp.file.cursor(N) %>`) que as skills preenchem: um **Roadmap**, os pares **Processed + Workbook** para Session, Mock Interview e Community, um **Template - Vaga** para preparação de vagas, e um **Template - Interview Question** para o banco de perguntas.

---

## Instalação

Assumindo que seu vault Obsidian também é o diretório do seu projeto Claude Code (como no setup original):

```bash
cd /caminho/pro/seu/vault

# 1. Skills — Claude Code procura skills em .claude/skills/
mkdir -p .claude/skills
cp -r /caminho/pro/gca-toolkit/skills/* .claude/skills/

# 2. Templates — vão na pasta de templates do vault
mkdir -p "00-Meta/templates/GCA"
cp /caminho/pro/gca-toolkit/templates/*.md "00-Meta/templates/GCA/"
```

Reinicie o Claude Code (ou rode `/help` para confirmar). Os comandos `/process-roadmap`, `/process-session`, `/process-mock-interview`, `/process-community`, `/coaching`, `/processar-vaga`, `/process-question`, `/seed-question` e `/glosa-video` devem aparecer.

> **Onde ficam as skills?** O Claude Code lê skills de `.claude/skills/<nome>/SKILL.md`. No meu setup, `.claude/skills` é um symlink pra `.agents/skills` (convenção minha) — você **não precisa** disso, pode usar `.claude/skills/` direto.

---

## Estrutura de pastas esperada no vault

As skills assumem esta árvore. **Os nomes das pastas estão hardcoded nas skills** — se a sua for diferente, veja [Como adaptar](#como-adaptar).

```
03-Domínios/Inglês/GCA/
├── <PDF do Cronograma>.pdf        ← fica na RAIZ do GCA
├── Roadmap.md                     ← gerado por /process-roadmap
├── Sessions/
│   ├── <PDFs de Session>.pdf
│   ├── Session NN - <Nome>.md            (Processed)
│   └── Session NN - <Nome> - Workbook.md
├── Mock Interview/
│   ├── <PDFs de Mock>.pdf
│   ├── Mock Interview NN - <Nome>.md
│   └── Mock Interview NN - <Nome> - Workbook.md
└── Community/
    ├── <PDFs de Community>.pdf
    ├── Community NN - <Nome>.md
    └── Community NN - <Nome> - Workbook.md

00-Meta/templates/GCA/            ← os 7 templates
```

> ⚠️ A pasta `Inglês` usa **acento** no setup original. Se o seu vault não tiver acento (ou usar outro idioma), ajuste os caminhos nas skills.

---

## Fluxo de uso recomendado

```
1. Coloque o PDF do Cronograma em 03-Domínios/Inglês/GCA/  →  /process-roadmap
                                                                    │
                          (Roadmap.md vira a fonte de inferência)   │
                                                                    ▼
2. A cada semana, jogue o PDF na pasta certa e rode:
     • PDF de Session   → Sessions/        → /process-session
     • PDF de Mock       → Mock Interview/   → /process-mock-interview
     • PDF de Community  → Community/        → /process-community
                                                                    │
3. Abra o Workbook gerado no Obsidian e comece a preencher os slots │
                                                                    ▼
4. Travou numa resposta?  → /coaching  (te guia, nunca escreve por você)
```

**Por que essa ordem?** `process-session` e `process-mock-interview` consultam o `Roadmap.md` pra inferir tema, persona, fase do funil e gerar cross-links automáticos. Se o Roadmap não existir, elas **degradam graciosamente** (avisam e perguntam os valores), mas o resultado é mais rico com ele.

---

## Como adaptar

O pacote foi escrito pro vault de uma pessoa específica. Aqui está **tudo que você provavelmente quer trocar**. Faça um find-and-replace nos arquivos `skills/**/SKILL.md` e `templates/*.md`.

### 1. Caminhos das pastas (o mais importante)

As skills referenciam caminhos literais. Se a sua estrutura difere, troque:

| Procure por | Troque pelo seu caminho |
|---|---|
| `03-Domínios/Inglês/GCA/Sessions/` | onde você guarda PDFs de Session |
| `03-Domínios/Inglês/GCA/Mock Interview/` | onde você guarda PDFs de Mock |
| `03-Domínios/Inglês/GCA/Community/` | onde você guarda PDFs de Community |
| `03-Domínios/Inglês/GCA/Roadmap.md` | onde fica seu MOC mestre |
| `00-Meta/templates/GCA/` | onde você colocou os templates |

> Dica: a forma mais simples é **manter a mesma estrutura de pastas** que o README descreve. Aí você não precisa editar nada de caminho.

### 2. Seu nome (detecção de participação na Community)

`process-community` procura o nome do aluno nos *room assignments* pra saber em quais rounds você participou e gerar os slots reflexivos. Abra `skills/process-community/SKILL.md` e troque a linha:

```
Procurar o nome do aluno (configurar: substituir pelo nome real do usuário do vault)
```

pelo **seu nome** (como ele aparece nos PDFs da Thaís).

### 3. Nome da mentora e do programa

Os 7 templates têm no frontmatter:

```yaml
mentora: Thaís Vieira
programa: Global Career Architecture (GCA)
```

Se você quiser personalizar (ou se for outra mentoria), troque nos `templates/*.md`. As skills também mencionam "Thaís Vieira" e "GSC/GCA" em exemplos — opcional trocar.

### 4. Número de semanas / ciclos

O programa original tem **12 semanas em 3 ciclos**. Isso aparece em:
- `process-roadmap` e o template `Roadmap.md` (estrutura de 12 semanas).
- Validações de range (`1-12`) em `process-session` e `process-mock-interview`.

Se a sua turma tiver outra duração, ajuste esses números.

### 5. Idioma

Conteúdo de entrevista (drafts, directives, Power Verbs) fica em **inglês**; instruções e coaching ficam em **PT-BR**. Se você estuda outro idioma-alvo, ajuste as convenções de output no fim de cada SKILL.md.

### 6. As regras GSC do `coaching`

A skill `coaching` tem uma tabela de regras (BLUF, Power Verbs, "I" não "We", show-don't-tell, sem narrativa de guerreiro, time-box, etc.) com citações tipo `Mock Interview 01.md#Q3`. Essas citações apontam pros **meus** arquivos. Você pode:
- Deixar como está (a skill cita o *seu* Processed correspondente ao trabalhar).
- Ou ajustar os exemplos pra refletir o feedback que **você** recebeu.

As regras em si (BLUF, Power Verbs, etc.) são gerais da mentoria — provavelmente valem pra você também.

### 6. Banco de perguntas (`process-question` + `seed-question`)

As skills de Q-bank assumem a pasta `03-Dominios/Inglês/Entrevistas/Database/`. Ajuste se a sua estrutura for diferente. O arquivo `Backlog de Perguntas.md` precisa existir antes de usar `/seed-question` — crie-o manualmente (seções `## Pendentes` e `## Processadas`).

### 7. Vagas (`processar-vaga`)

Copia o `Template - Vaga.md` pra `00-Meta/templates/Template - Vaga.md` (raiz dos templates, não subpasta GCA). A pasta de vagas esperada é `03-Dominios/Inglês/Entrevistas/Vagas/` — crie se não existir.

### 8. Glosas de vídeo (`glosa-video`)

Requer `uvx` (instalado via `uv`). Salva glosas em `02-Glosas/`. Ajuste o caminho se seu vault tiver estrutura diferente.

### Checklist rápido de adaptação

- [ ] Conferir/ajustar os caminhos de pasta nas skills
- [ ] Trocar seu nome em `process-community` (linha com "nome do aluno")
- [ ] (Opcional) Ajustar `mentora:` / `programa:` nos templates
- [ ] (Opcional) Ajustar número de semanas/ciclos se sua turma for diferente
- [ ] Copiar templates pra `00-Meta/templates/GCA/` (exceto Template - Vaga → raiz de templates)
- [ ] Copiar skills pra `.claude/skills/`
- [ ] Rodar `/process-roadmap` com o PDF do Cronograma e validar

---

## Princípios de design (por que as skills se comportam assim)

- **Nunca inventam conteúdo.** Se o PDF não traz uma seção, a skill deixa de fora ou marca com placeholder claro. Não tem "achismo".
- **Nunca escrevem a sua resposta.** Todos os slots de Draft no Workbook ficam vazios. O `coaching` é socrático estrito — dar a resposta pronta é considerado *fracasso total da tarefa*.
- **Nunca sobrescrevem trabalho seu sem confirmar.** Se um Workbook já tem conteúdo manual, a skill pede confirmação reforçada.
- **Degradação graciosa.** Sem Roadmap? A skill avisa e segue perguntando o que precisa, em vez de quebrar.
- **Markdown puro na saída.** A nota final nunca tem sintaxe Templater sobrando — se sobrar, a skill aborta antes de gravar (é sinal de bug de mapeamento).

---

## Licença / uso

Material de estudo pessoal, compartilhado de graça entre colegas de mentoria. Use, adapte e melhore à vontade. Os PDFs e o conteúdo da mentoria pertencem à Thaís Vieira / GCA — este toolkit só processa o que **você** já recebeu, no **seu** vault.

Bons estudos e boa sorte nas entrevistas. 🚀
