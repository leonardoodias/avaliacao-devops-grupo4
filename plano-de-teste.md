# Plano de teste

## Fase de Planejamento
  - Teste estático com revisão de documentação

    No teste estático, a revisão é um processo ou técnica que é executado para encontrar os defeitos potenciais no design do software. É um processo que detecta e remove erros e defeitos nos diferentes documentos de suporte, como especificações de requisitos de software. As pessoas examinam os documentos e classificam os erros, redundâncias e ambigüidades.
    
    - Informal:

      Na revisão informal, o criador dos documentos expõe o conteúdo ao público e todos dão sua opinião e, assim, os defeitos são identificados na fase inicial.
    - Passo a passo:

      Basicamente, é realizado por uma pessoa experiente ou especialista para verificar os defeitos para que não haja mais problemas na fase de desenvolvimento ou teste.
    
    - Revisão por pares: 
    
      A revisão por pares significa verificar os documentos uns dos outros para detectar e corrigir os defeitos. Basicamente, é feito em uma equipe de colegas.
    
    - Inspeção: 
    
      A inspeção é basicamente a verificação do documento da autoridade superior, como a verificação das especificações de requisitos de software (SRS)

## Fase de Desenvolvimento 
  - Teste unitário com técnicas de TDD
    
    Desenvolvimento orientado a teste é um processo no qual você escreve o teste antes de escrever o código. E quando todos os testes estão passando você limpa sua cozinha: você melhora o código.

  - Teste de API.

    As estratégias de teste de API são semelhantes a outras metodologias de teste de software. O principal foco é validar as respostas do servidor.

## Fase de Geração de build 
  - Teste de integração utilizando alguma estratégia, como _Bottom-Up_.

    O teste de integração é uma atividade sistemática que tem como objetivo verificar a construção da estrutura do software que está sendo desenvolvido e a sua comunicação entre módulos. 

  - Teste E2E

    O teste end-to-end é uma metodologia utilizada para testar se o fluxo de um aplicativo está sendo executado conforme o projeto do início ao fim. O objetivo da realização de testes end-to-end é identificar dependências do sistema e garantir que a informação certa seja passada entre vários componentes e sistemas do sistema.



## Fase de Deploy em ambiente de homologação 
  - Teste de regressão

    Acontece quando à introdução de características novas ou alteradas, diz-se que regressou a um estado menos desenvolvido. Mesmo pequenas alterações ao software ou ao código original podem resultar em erros significativos, tais como falhas, falhas, e perda parcial ou total de funcionalidade.

  - Teste Exploratório

    Testes exploratórios é a abordagem para testes de software que, com frequência, é descrita como aprendizagem simultânea, design de teste e execução. O foco está na descoberta e depende da orientação do testador individual para descobrir defeitos que não são abrangidos com facilidade no escopo de outros testes.

  - Teste de carga.

    O teste de carga simula cenários do mundo real em seus sites, aplicativos e sistemas. Através das informações coletadas durante e após os testes de carga, os desenvolvedores podem medir os limites e obter insights sobre as métricas 

## Fase de Deploy de produção 
  - Smoke teste

    Smoke testing ou teste de fumaça são testes básicos que verificam as funcionalidade básicas da aplicação, é um processo que deve ser executado de forma rápida para determinar se o build ou a compilação da aplicação realizada está estável ou não



  #### Fontes
  - [Teste estático](https://acervolima.com/teste-de-software-teste-estatico/)
  - [Teste API](https://aws.amazon.com/pt/what-is/api/)
  - [Teste Integração](https://kenzie.com.br/blog/teste-de-integracao/)
  - [Teste E2E](https://www.cedrotech.com/blog/teste-end-to-end/)
  - [Teste Regressão](https://www.zaptest.com/pt-br/o-que-e-o-teste-de-regressao-implementacao-ferramentas-e-guia-completo)
  - [Teste Exploratório](https://www.atlassian.com/br/continuous-delivery/software-testing/exploratory-testing)
  - [Teste de carga](https://www.loadview-testing.com/pt-br/teste-de-carga/)
  - [Smoke teste](https://www.bing.com/search?q=Smoke+teste&cvid=89cac4393faa4c73a8472ccf205a62b7&aqs=edge..69i57.199j0j1&pglt=43&FORM=ANNTA1&PC=U531)