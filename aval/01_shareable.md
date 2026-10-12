# Projeto da Disciplina — Análise e Projeto de Sistemas

Oct 12, 2026 · @Anthony Irlan Marques Luz

## Apresentação

Cada equipe vai projetar e construir, ao longo do semestre, um sistema desktop em Java com banco de dados local. A cada semana a equipe entrega **um diagrama UML e o código que implementa exatamente o que esse diagrama especifica**.

O objetivo é que o diagrama deixe de ser um desenho feito depois do código e passe a ser a especificação que guia o código. Por isso, todo commit de entrega precisa ser rastreável até um elemento de um diagrama.

- **Equipes:** até 4 integrantes.
- **Tema:** livre, desde que atenda aos requisitos mínimos de complexidade da próxima seção.
- **Entregas:** semanais, pelo repositório da equipe no GitHub.
- **Ponto de partida:** as histórias de usuário levantadas na elicitação de requisitos, organizadas por papel, formam o Product Backlog inicial e originam os casos de uso da semana 1.

## Requisitos mínimos de complexidade

O sistema precisa ter conteúdo suficiente para que cada diagrama do semestre seja necessário. Um sistema feito apenas de cadastros (CRUD) não atende: os diagramas de sequência, atividades e estados ficariam artificiais.

| Dimensão | Mínimo | Teto sugerido |
| --- | --- | --- |
| Atores (perfis de usuário) | 3 | 6 |
| Casos de uso | 12 | 20 |
| Casos de uso que são CRUD puro | no máximo metade | — |
| Classes de domínio | 9 | 13 |
| Entidade com ciclo de vida | 1, com pelo menos 4 estados | 2 |
| Regras de negócio com cálculo ou validação | 2 | — |
| Autenticação com perfis de acesso | obrigatória | — |

## Tecnologias obrigatórias

| Camada | Tecnologia | Observação |
| --- | --- | --- |
| Linguagem | Java 21 | Versão LTS |
| Interface gráfica | Sua escolha | — |
| Banco de dados | SQLite via `sqlite-jdbc` | Arquivo local, criado pelo próprio sistema na primeira execução |
| Persistência | JDBC | — |
| Build | Maven | O sistema deve executar com `mvn javafx:run` |
| Versionamento | Git + GitHub | Issues ou GitHub Projects como Product Backlog |

## Entrega da semana 1

A semana 1 tem três partes: o repositório, o documento de casos de uso e o diagrama de casos de uso.

**1. Repositório**

- [ ] Repositório no GitHub com todos os integrantes e o professor como colaboradores
- [ ] Projeto Maven inicial com JavaFX e `sqlite-jdbc` no `pom.xml`, executando uma tela vazia com `mvn javafx:run`
- [ ] README com nome do sistema, tema, integrantes e instruções de execução
- [ ] Pasta `docs/` para os diagramas e documentos
- [ ] Histórias de usuário cadastradas como issues (ou cards no GitHub Projects), ordenadas por prioridade

**2. Documento de casos de uso** (`docs/casos-de-uso.md` ou PDF)

- Visão geral do sistema em um parágrafo
- Lista de atores com a descrição de cada um
- Lista de todos os casos de uso, com identificador (UC01, UC02…), nome e ator principal
- Rastreabilidade: cada caso de uso indica de quais histórias de usuário ele se origina

Modelo de especificação: Livro didático, como mostrado em sala.

**3. Diagrama de casos de uso** (`docs/diagramas/casos-de-uso.png`, com o arquivo-fonte)

- Fronteira do sistema, todos os atores e todos os casos de uso listados no documento
- Uso de `<<include>>` e `<<extend>>` apenas onde existe a relação de fato
- Ferramenta livre, desde que o arquivo-fonte esteja no repositório

## Critérios de avaliação

O critério central é a **rastreabilidade**: cada elemento do diagrama da semana aparece no código, e o código não tem comportamento relevante ausente do diagrama.

| Critério | Peso |
| --- | --- |
| Correção do diagrama (notação UML e semântica) | 30% |
| Rastreabilidade diagrama ↔ código | 30% |
| Código funcionando e executável com `mvn javafx:run` | 25% |
| Organização do repositório e dos commits | 15% |

Todo commit de entrega cita o elemento que implementa, por exemplo: `Implementa DS-01: Realizar saque`. Entregas sem código executável serão zeradas.
