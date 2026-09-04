# 🧬 Árvore de Habilidades — Licenciatura em Ciências Biológicas (UFV)

Subprojeto que aplica a mesma ideia da [árvore de habilidades da grade de Ciência da Computação da UFJF](../README.md) — o projeto principal deste repositório — ao currículo da **Licenciatura em Ciências Biológicas da Universidade Federal de Viçosa (UFV)**.

> ⚠️ **Este é um subprojeto derivado**, gerado a partir da mesma ferramenta e lógica do site principal, mas para outra grade curricular. Por isso ele **fica propositalmente oculto da navegação normal da página principal** (que é a árvore da grade de CC da UFJF) — não há link apontando para cá a partir do `index.html` raiz. O acesso é direto pela URL desta pasta.

## 🎯 Objetivo

Assim como no projeto principal, a ideia é transformar uma matriz curricular densa (aqui, extraída do Catálogo de Graduação da UFV) em um **grafo de dependências navegável**, no estilo de uma árvore de habilidades de RPG, deixando claro:

- Quais disciplinas uma disciplina específica libera ao ser concluída;
- Quais já estão disponíveis para cursar *agora*, dado o que já foi concluído;
- Como fica o desbloqueio de disciplinas futuras caso outras sejam cursadas antes.

## ✨ O que este subprojeto tem de diferente

Tanto a grade de CC (projeto principal) quanto esta de Ciências Biológicas têm uma seção de disciplinas eletivas/optativas recolhível, agrupada por categoria, com setas de dependência cruzando para a grade obrigatória e uma barra de progresso própria — essa mecânica hoje é comum aos dois sites. O que continua sendo específico deste subprojeto é a complexidade bem maior do currículo da UFV:

- **47 disciplinas obrigatórias** (10 períodos, 2685h) **+ 153 disciplinas optativas** (meta de 500h) — quase o dobro das 94 eletivas da grade de CC.
- **Cores por departamento** (BAN, BIO, BQI, BVE, EDU, MBI, QUI, SOL...), um esquema mais granular que as poucas áreas de formação/conhecimento usadas na grade de CC.
- Um **parser de pré-requisitos com "e" / "ou" / parênteses**, já que aqui é comum ter regras como `(BQI 100 ou BQI 103 ou BQI 211) e (BIO 220* ou BIO 221*)` — a grade de CC não precisa disso porque seus pré-requisitos são sempre listas simples ("e" implícito).
- Suporte a **correquisitos** (marcados com `*` no catálogo, quando a disciplina pode ser cursada junto do pré-requisito, sem bloquear uma a outra) — recurso que a grade de CC não usa.
- Pré-requisitos que referenciam **códigos fora deste catálogo** (disciplinas legadas ou de outros cursos, ex: `BQI 100`, `MBI 102`) são tratados como não verificáveis e não contam como cumpridos, para não abrir brechas na árvore.

O restante da mecânica é idêntico ao projeto principal: clique para marcar como concluída, progresso salvo no `localStorage` do navegador, Modo Simulação, busca (que também revela automaticamente a eletiva/optativa correspondente), tooltips com pré-requisitos e o que cada disciplina libera.

## 🕹️ Como usar

Veja as instruções de uso no [README do projeto principal](../README.md#🕹️-como-usar) — a interação é a mesma, incluindo o botão equivalente ao "Mostrar Eletivas" de lá: aqui ele se chama **Mostrar Optativas** e revela as 153 disciplinas optativas agrupadas por departamento.

## 🗂️ Fonte dos dados

Disciplinas, cargas horárias e pré-requisitos foram extraídos do **Catálogo de Graduação da UFV** (campus Viçosa), currículo da Licenciatura em Ciências Biológicas.

## 🤖 Sobre este projeto

Assim como o site principal, este subprojeto foi desenvolvido com o auxílio do **[Claude Code](https://claude.com/claude-code)**: a extração dos dados do catálogo em PDF, a modelagem dos pré-requisitos (incluindo o parser de expressões lógicas) e toda a implementação em HTML/CSS/JS foram feitas com a colaboração do Claude Code, reaproveitando e adaptando a lógica criada originalmente para a grade de Ciência da Computação da UFJF.

## ⚠️ Aviso

Este projeto é uma ferramenta de apoio criada por um estudante e **não substitui o catálogo oficial da UFV**. Sempre confirme pré-requisitos e integralização junto à coordenação do curso e ao sistema acadêmico oficial da UFV.
