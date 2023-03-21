# Documento de Padrões de Issue e Nomenclatura para Desenvolvimento de Software

Este documento descreve o padrão de nomenclatura e informações que devem ser incluídas em cada issue no desenvolvimento de software, a fim de melhorar a comunicação e o gerenciamento de projetos.


## Padrão da Issue

1. '**Título da issue**'
O título da issue deve ser breve, mas descritivo o suficiente para identificar claramente o problema ou recurso a ser implementado. Deve ser escrito em inglês e seguir o padrão CamelCase (ou seja, as palavras começam com letra maiúscula e não há espaço entre elas). Alguns exemplos de títulos para issues são:

- UpdateUserProfile
- AddPaymentMethod
- FixLoginError

2. '**Descrição da issue**'
A descrição da issue deve conter informações detalhadas sobre o problema ou recurso a ser implementado, incluindo o contexto em que ocorre, a gravidade do problema ou a importância do recurso e quaisquer requisitos ou limitações específicos. Deve ser escrita em inglês e seguir o padrão de linguagem natural.

3. '**Tipo de issue**'
O tipo de issue deve ser definido com base na natureza do problema ou recurso a ser implementado. Alguns exemplos de tipos de issue incluem:

- '**Bug:**' problema com o código que impede o funcionamento adequado do software.
- '**Feature:**' novo recurso ou funcionalidade a ser adicionado ao software.
- '**Enhancement:**' melhoria em uma funcionalidade existente no software.
- '**Documentation:**' atualização ou adição de documentação.
- '**Test:**' criação ou atualização de testes.

4. '**Prioridade**'
A prioridade da issue deve ser definida com base na gravidade do problema ou na importância do recurso. A escala de prioridade deve ser claramente definida, por exemplo, alta, média e baixa. Alguns exemplos de prioridades de issue incluem:

- '_Alta_': problema crítico que impede o funcionamento do software ou recurso essencial para o negócio.
- '_Média_': problema que afeta o uso do software ou recurso importante para o negócio.
- '_Baixa_': problema que afeta o uso do software ou recurso de baixa prioridade para o negócio.

5. '**Responsável**'
O responsável pela issue deve ser atribuído a um membro específico da equipe de desenvolvimento, que será responsável por resolver a issue. Isso ajuda a garantir que as issues sejam tratadas de forma eficiente e que todas as partes interessadas sejam mantidas informadas sobre o progresso.

6. '**Estimativa de tempo**'
A estimativa de tempo deve ser definida com base na complexidade da issue e no tempo necessário para resolvê-la. Deve ser uma estimativa realista, levando em consideração o nível de experiência do responsável pela issue e quaisquer outros fatores relevantes. A unidade de medida deve ser claramente definida, por exemplo, horas ou dias.

7. '**Data de criação**'
A data em que a issue foi criada deve ser registrada.

8. '**Status**'
O status da issue deve ser atualizado regularmente para refletir o progresso da issue. Alguns exemplos de status de issue incluem:

- '_To Do_': issue ainda não iniciada.
- '_In Progress_': issue em andamento.
- '_Blocked_': issue impedida por outro problema ou recurso que ainda não foi resolvido.
- '_Done_': issue foi concluída.


## Padrão de Nomenclatura

Para estabelecer um padrão de nomenclatura de issues, é importante levar em consideração que o nome deve ser claro e descritivo o suficiente para que todos os membros da equipe possam entender o problema e sua solução proposta.

Um padrão comum é utilizar um prefixo que indique o tipo de tarefa, seguido por um número e um resumo descritivo do problema ou funcionalidade. Além disso, é possível adicionar mais informações relevantes, como o nome do projeto ou módulo ao qual a tarefa se refere, palavras-chave para indicar a prioridade ou gravidade da tarefa, tags ou labels que ajudem a categorizar as tarefas, um sistema de numeração sequencial e informações sobre o estado atual da tarefa.

Considerando o padrão de nomenclatura de issues aprimorado, é possível adicionar informações relevantes para facilitar a identificação da tarefa. 
Algumas delas que iremos utilizar:

- Incluir o nome do projeto ou módulo ao qual a tarefa se refere: por exemplo, "PROJETO-A-BUG-123" ou "MODULO-B-FEATURE-456"
- Prefixos para variar de acordo com a preferência da equipe
    - '**BUG-123:**' Corrigir erro de login
    - '**FEATURE-456:**' Adicionar suporte a autenticação via Google
    - '**IMPROVEMENT-789:**' Otimizar a velocidade de carregamento da página inicial
    - '**TASK-321:**' Atualizar documentação de instalação
- Utilizar palavras-chave para indicar a prioridade ou gravidade da tarefa, como '**"HIGH"**' ou '**"LOW"**'
- Incluir tags ou labels que ajudem a categorizar as tarefas, como '**"BACKEND"**', '**"FRONTEND"**', '**"DATABASE"**', entre outras
- Utilizar um sistema de numeração sequencial para facilitar a identificação e organização das tarefas
- Incluir informações sobre o estado atual da tarefa, como '**"OPEN"**', '**"IN PROGRESS"**' ou '**"CLOSED"**'

## Exemplo de uma nomenclatura de issue aprimorada:
 - '**PROJETO A - BACKEND - BUG-123 -LOGIN-ERROR-HIGH-OPEN**'

Nesse exemplo, incluímos informações sobre o projeto, a área do sistema afetada (backend), o tipo de tarefa (bug), um resumo descritivo da tarefa (login error), a prioridade (alta) e o estado atual (aberta). Isso torna mais fácil para a equipe identificar rapidamente do que se trata a tarefa e tomar as medidas necessárias para resolvê-la.
