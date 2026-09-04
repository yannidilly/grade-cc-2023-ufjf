# 🎓 Árvore de Habilidades — Ciência da Computação (UFJF)

Uma visualização interativa, em estilo de **árvore de habilidades de RPG**, da matriz curricular do curso de **Ciência da Computação Integral da UFJF** (versão 2023). O objetivo é tornar visíveis, de forma rápida e visual, as dependências entre as disciplinas — o que cada uma trava e destrava — e ajudar no planejamento de quais matérias cursar em cada período.

🔗 **[Acesse o site aqui](https://yannidilly.github.io/grade-cc-2023-ufjf/)**

---

## 🎯 Objetivos

A matriz curricular oficial mostra os pré-requisitos de cada disciplina em formato de tabela, o que dificulta enxergar rapidamente:

- Quais matérias uma disciplina específica libera ao ser concluída;
- Qual é o "caminho crítico" do curso (ex: Algoritmos → Algoritmos II → Estrutura de Dados → ...);
- Quais disciplinas já estão liberadas para cursar _agora_, dado o que já foi concluído;
- Como ficaria o desbloqueio de matérias futuras se determinadas disciplinas fossem cursadas antes do previsto.

Este projeto resolve isso transformando a grade em um **grafo de dependências navegável**, no espírito de uma árvore de habilidades de jogos de RPG: nós conectados por setas, bloqueados por cadeados até que os pré-requisitos sejam cumpridos, e organizados nas colunas de período recomendadas pela grade oficial.

## ✨ Funcionalidades

- **Colunas por período (1º ao 8º)**, seguindo a recomendação oficial da grade.
- **Setas de dependência** entre disciplinas, indicando visualmente o que cada matéria trava/destrava.
- **Cores por área de formação** (Básica, Tecnológica, Humanística, Complementar), consistentes em toda a árvore.
- **Estados visuais das disciplinas**:
  - 🔒 **Bloqueada** — pré-requisitos ainda não cumpridos;
  - ⭐ **Disponível** — pode ser cursada agora (nó com brilho dourado pulsante);
  - ✔️ **Concluída** — marcada como já cursada (verde);
  - ⏳ **Planejada** — usada no modo simulação (azul tracejado).
- **Marcar matérias como concluídas** com um clique — o progresso é salvo automaticamente no `localStorage` do navegador (nada é enviado para servidor nenhum).
- **Modo Simulação**: permite planejar disciplinas futuras sem alterar seu progresso real, mostrando em cascata o que seria desbloqueado.
- **Tooltip ao passar o mouse**, com nome completo, carga horária, pré-requisitos (com indicação do que já foi cumprido) e quais disciplinas aquela matéria libera.
- **Barra de progresso** com total de horas obrigatórias concluídas.
- **Busca** por nome ou código da disciplina.
- Tratamento de casos especiais, como o **TCC I**, que exige 1560 horas cursadas além do pré-requisito de Metodologia Científica.

## 🕹️ Como usar

1. Abra o site.
2. Clique em uma disciplina **disponível** (borda dourada) para marcar como **concluída**. Ela ficará verde e as disciplinas que dependiam dela poderão ser destravadas.
3. Clique em uma disciplina **concluída** para desmarcá-la, caso tenha errado.
4. Passe o mouse sobre qualquer disciplina para ver seus pré-requisitos e o que ela desbloqueia.
5. Ative o **Modo Simulação** no topo da página para planejar o futuro: as disciplinas marcadas nesse modo não são salvas, servem apenas para visualizar cenários (ex: "se eu pegar Banco de Dados e Engenharia de Software, o que mais se abre?").
6. Use **Limpar simulação** para descartar o planejamento, ou **Resetar progresso** para apagar tudo o que foi marcado como concluído.
7. Use a busca no topo para localizar rapidamente uma disciplina pelo nome ou código (ex: `DCC013`).

> Seu progresso fica salvo **apenas no seu navegador** (via `localStorage`). Limpar os dados do site no navegador, ou acessar de outro dispositivo/navegador, reinicia o progresso.

## 🗂️ Fonte dos dados

As disciplinas, cargas horárias, áreas de formação e pré-requisitos foram extraídos do documento oficial **"Matriz Curricular 2023 - Ciência da Computação Integral"** da UFJF (arquivo PDF incluído neste repositório).

## 🛠️ Tecnologias

Site estático de **arquivo único** (`index.html`), sem build, sem dependências de backend e sem frameworks — apenas HTML, CSS e JavaScript puro (SVG para as setas de dependência). Isso o torna ideal para hospedagem no **GitHub Pages**.

## 🤖 Sobre este projeto

Este site foi desenvolvido com o auxílio do **[Claude Code](https://claude.com/claude-code)**, ferramenta de codificação assistida por IA da Anthropic: a extração dos dados do PDF da matriz curricular, o design da árvore de habilidades e toda a implementação em HTML/CSS/JS foram feitos com a colaboração do Claude Code.

## ⚠️ Aviso

Este projeto é uma ferramenta de apoio criada por um estudante e **não substitui a matriz curricular oficial**. Sempre confirme pré-requisitos e integralização junto à coordenação do curso e ao sistema acadêmico oficial da UFJF.
