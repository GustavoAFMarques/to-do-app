# Documentação do Projeto: To-Do List

## Visão Geral
Este projeto é um To-Do List funcional desenvolvido como parte do Desafio: IA no Desenvolvimento de Software. A atividade integra a disciplina de Engenharia de Prompt aplicada ao Ciclo de Vida do Software, ministrada pelo Prof. Msc. Alexander Gobbato. 

O processo de desenvolvimento foi guiado por Engenharia de Prompt, utilizando a Inteligência Artificial como um assistente de programação (Pair Programming). O foco do desafio manteve-se no aprendizado, na geração consciente de código e no pensamento crítico para avaliar e justificar os requisitos transformados em interface.

---

## Requisitos Implementados

O sistema cumpre todos os requisitos base estabelecidos na documentação do desafio:

* **Campo de Entrada:** Local dedicado para digitar a descrição da nova tarefa.
* **Seletor de Prioridade:** Opções para definir a urgência da tarefa em três níveis: Alta, Média ou Baixa.
* **Lista de Exibição:** Interface onde as tarefas cadastradas aparecem dinamicamente.
* **Ação de Conclusão:** Mecanismo integrado para marcar a tarefa como finalizada.
* **Estilização Condicional:** Cores e elementos visuais que mudam automaticamente conforme a prioridade atribuída à tarefa.

---

## Funcionalidades Avançadas da Interface

A aplicação contida no arquivo `index.html` vai além dos requisitos básicos e implementa uma arquitetura completa de gerenciamento de tarefas:

### Gerenciamento de Estado
* **Contador de Pendências:** Atualização em tempo real do número de tarefas que ainda não foram concluídas.
* **Filtros de Visualização:** Botões que permitem isolar a exibição da lista com base na prioridade (Todas, Alta, Média, Baixa), com contadores individuais para cada categoria.
* **Paginação:** Sistema automático que limita a visualização a 5 tarefas por página, criando controles de navegação inferior quando o limite é excedido.

### Painel de Detalhes da Tarefa
Cada item da lista possui um painel oculto que pode ser expandido para revelar opções avançadas:
* **Status Manual:** Dropdown para alterar o estado entre "Não iniciado", "Em progresso" e "Completo" (sincronizado com a checkbox principal).
* **Rótulos (Labels):** Campo de texto para categorização personalizada (ex: Design, Backend).
* **Recorrência:** Toggle switch para marcar se uma tarefa deve se repetir.
* **Vencimento:** Seletor de data. O sistema calcula automaticamente se a tarefa está no prazo ou exibe um aviso em vermelho caso esteja atrasada.
* **Notas:** Área de texto expandida para anotações extras sobre a tarefa.

---

## Arquitetura e Estrutura de Código

O desenvolvimento do sistema foi consolidado em um único arquivo de entrega (`index.html`), estruturado da seguinte forma:

### HTML Semântico
A estrutura utiliza tags semânticas (`<header>`, `<main>`, `<section>`, `<ul>`, `<li>`) garantindo uma organização lógica e acessível. Foram incluídos atributos ARIA (`aria-label`, `aria-live`, `role`) para melhorar o suporte a leitores de tela.

### CSS Customizado e Design System
O layout foi construído com foco em legibilidade e hierarquia visual, operando em um tema noturno (Dark Mode).
* **Variáveis (Tokens):** Uso intensivo de CSS Custom Properties (`:root`) para centralizar a paleta de cores (tons de azul marinho e cyan), espaçamentos e raios de borda.
* **Responsividade:** O layout adapta seus elementos internos e tipografia em telas menores utilizando Media Queries.
* **Animações:** Transições suaves em interações de hover, expansão de menus e na inserção/remoção de elementos da lista (`@keyframes slideIn`).

### Lógica Funcional (JavaScript)
Para garantir o comportamento dinâmico e o gerenciamento das interações dos usuários, um bloco de script foi implementado. Ele é responsável por:
* Capturar os dados do formulário de entrada.
* Gerar o HTML de novos itens da lista de forma dinâmica.
* Gerenciar eventos de clique, alteração de estado e exclusão de itens.
* Processar a lógica matemática de atrasos de data e fatiamento de arrays para a paginação.
