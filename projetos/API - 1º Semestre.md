#### Em 2023-2

**Empresa**: _FATEC São José dos Campos - SP_
Profº Antônio Egydio São Tiago Graça

#### Problema: 
A empresa parceira identificou dificuldades na aplicação da metodologia ágil Scrum por parte de seus colaboradores. A falta de entendimento sobre os papéis, eventos e artefatos da metodologia tem gerado ruídos de comunicação entre as equipes, atrasos nas entregas e baixa colaboração entre os membros. Essa defasagem de conhecimento impacta diretamente a produtividade e a qualidade das entregas, dificultando a adoção eficiente de práticas ágeis no ambiente organizacional.

#### Solução:
Desenvolvimento de uma aplicação web voltado à formação de pessoas na metodologia **Scrum**, possibilitando também a **avaliação de integrantes da própria equipe**. O objetivo é capacitar o usuário a aplicar os princípios do Scrum em situações reais do seu cotidiano profissional.


##### [Repositório](https://github.com/Phoenix-Team-Fatec/ScrumTutor)

#### Tecnologias Utilizadas
| **Tecnologia** | **Funcionalidade**                                                                  |
| -------------- | ----------------------------------------------------------------------------------- |
| **HTML**       | Define a estrutura e o conteúdo das páginas web.                                    |
| **CSS**        | Responsável pela estilização e layout das páginas.                                  |
| **Flask**      | Framework web em Python utilizado para criar e gerenciar o servidor da aplicação.   |
| **Python**     | Linguagem de programação utilizada no desenvolvimento do backend com Flask.         |
| **AWS**        | Plataforma de nuvem utilizada para hospedagem e deploy da aplicação web.            |
| **Figma**      | Ferramenta de prototipação para o design da interface e fluxo de navegação do site. |
| **Git**        | Sistema de controle de versão utilizado para gerenciar e versionar o código-fonte.  |

## Contribuições Pessoais
Atuando como desenvolvedor no projeto, fui responsável pela implementação e estilização das páginas Papéis, Bibliografia e Apêndice, além dos componentes Menu, Submenu e dos formulários de avaliação PACER. O PACER consiste em uma avaliação de zero a quatro nos seguintes tópicos: proatividade, autonomia, colaboração e entrega de resultados. Todos os componentes foram desenvolvidos utilizando templates do framework Flask.
Também contribuí no desenvolvimento da lógica de envio dos formulários e na resolução de conflitos de versionamento utilizando Git. Em um dos casos, resolvi conflitos nos arquivos style.css e artefatos.html, ocasionados pela edição simultânea do mesmo trecho de código por dois integrantes do grupo. Para solucionar o problema, removi duplicidades e mantive a versão correta de cada trecho.
Por fim, realizei a hospedagem da aplicação na AWS, configurando a instância, executando o build do projeto e instalando todas as dependências necessárias para o funcionamento do sistema.

## Hard Skills
| Tecnologia | Proficiência       | Descrição                                                                           |
| :--------- | :----------------- | :---------------------------------------------------------------------------------- |
| **HTML**   | faço com autonomia | Estruturação semântica e acessível de páginas web.                                  |
| **CSS**    | faço com autonomia | Estilização e criação de layouts responsivos e modernos com Flexbox/Grid.           |
| **Flask**  | faço com ajuda     | Desenvolvimento de aplicações web,renderização de templates dinâmicos.              |
| **Python** | faço com autonomia | Desenvolvimento da lógica de back-end, manipulação de dados e automação de scripts. |
| **AWS**    | faço com ajuda     | Implantação e hospedagem de aplicações em serviços cloud (EC2).                     |
| **Git**    | faço com autonomia | Controle de versão, trabalho em equipe com branches e gestão de repositórios.       |
| **Figma**  | faço com ajuda     | Prototipagem de interfaces de usuário (UI)                                          |

## Soft Skills
- **Comunicação**: *Durante uma daily scrum, o grupo apresentava dificuldades em definir a pergunta adequada para esclarecer uma regra de negócio com o cliente. Essa regra estava relacionada à forma como o conteúdo sobre o framework Scrum seria apresentado aos usuários, envolvendo tanto a organização das páginas quanto o mapa de navegação da aplicação. Ao perceber a falta de alinhamento entre os integrantes, sugeri que estruturássemos previamente as telas do sistema e o conteúdo previsto em cada uma delas. Essa organização facilitou a compreensão do contexto geral e permitiu formular uma pergunta clara e objetiva ao cliente, que, por sua vez, conseguiu explicar de maneira precisa a regra necessária para o desenvolvimento da funcionalidade.*

- **Trabalho em Equipe**: *Um dos requisitos do projeto era desenvolver o sistema de formulários que permitia ao usuário avaliar os membros de sua equipe com base no PACER. Durante essa etapa, um integrante do grupo encontrou dificuldades para implementar a lógica de recebimento e tratamento dos dados enviados pelo elemento `<form>` do HTML. Colaborei diretamente com ele na construção dessa lógica utilizando Python e o framework Flask, discutindo alternativas, dividindo tarefas e revisando o fluxo de dados.
O principal desafio era estruturar a captura das notas preenchidas no formulário e organizá-las em objetos. Para resolver esse problema, desenvolvemos juntos uma rotina que recebia os valores enviados via request.form, organizando-os em listas separadas para cada critério do PACER (proatividade, autonomia, colaboração e entrega). Além disso, adicionamos dinamicamente as avaliações referentes aos desenvolvedores de teste (D.T), utilizando um laço for para percorrer a quantidade de membros definida no sistema.
Após coletar todos os valores, implementamos a criação de objetos da classe avaliacao, nos quais cada instância representava a avaliação individual de um papel da equipe (P.O, S.M ou D.T). Esses objetos eram armazenados no vetor notas, garantindo que todas as informações estivessem estruturadas corretamente para posterior exibição ou processamento.
Ao trabalhar em conjunto nessa implementação, conseguimos finalizar a funcionalidade de forma eficiente, fortalecendo a cooperação, o aprendizado mútuo e o ritmo de desenvolvimento do grupo.*



[Voltar](../README.md)
