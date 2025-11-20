#### Em 2025-1

**Empresa**: FAPG (Fundação de Apoio à Pesquisa e Gestão) 
<br>
**Área de atuação**: Pesquisa de pós graduação
#### Problema: 
A empresa parceira enfrenta dificuldades no gerenciamento e acompanhamento dos projetos em desenvolvimento. A ausência de um processo padronizado de planejamento e controle tem resultado em falhas no levantamento de requisitos, atrasos nas entregas e dificuldades na alocação de recursos financeiros. Essa falta de visibilidade sobre o andamento das atividades compromete o cumprimento de prazos e afeta a eficiência geral da gestão de projetos.

#### Solução:
Foi desenvolvida uma aplicação web para o gerenciamento de projetos, permitindo o cadastro de nome, descrição, datas, orçamento e participantes.  
Cada projeto possui etapas e tarefas que podem ser atribuídas a membros específicos, possibilitando o acompanhamento detalhado do progresso.  
O sistema conta com uma funcionalidade de lixeira, onde projetos excluídos permanecem disponíveis por 30 dias para possível restauração.  
As tarefas são exibidas em uma tabela com informações como prazo, status e projeto associado.  
Além disso, foi implementado um chatbot interativo que permite atualizar o status das tarefas para “concluída” ou “em andamento” de forma dinâmica e intuitiva.

##### [Repositório](https://github.com/Phoenix-Team-Fatec/API-4)

| **Tecnologia** | **Funcionalidade**                                                                                                                               |
| :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **React**      | Biblioteca JavaScript utilizada para o desenvolvimento do frontend da aplicação, permitindo a criação de interfaces dinâmicas e componentizadas. |
| **Node.js**    | Ambiente de execução JavaScript multiplataforma, utilizado para rodar o código no servidor.                                                      |
| **JavaScript** | Linguagem de programação utilizada no desenvolvimento do projeto, responsável pela lógica de interação e integração entre os componentes.        |
| **TypeScript** | Superset do JavaScript que adiciona tipagem estática e recursos de orientação a objetos, aumentando a robustez e a manutenção do código.         |
| **PostgreSQL** | Banco de dados relacional, utilizado para armazenamento de dados do sistema                                                                      |
| **Firebase**   | Serviço em nuvem com banco de dados não relacional (NoSQL), utilizado para o armazenamento e autenticação de usuários (e-mails e senhas).        |
| **Ollama**     | Ferramente utilizada para executar e gerenciar modelos                                                                                           |
| **Git**        | Sistema de controle de versão distribuído, utilizado para o gerenciamento do código-fonte e colaboração em equipe.                               |
## Contribuições Pessoais
*Atuando como Product Owner, fui responsável pela documentação do projeto no GitHub, onde organizei e mantive o Product Backlog, detalhei histórias de usuário e realizei a priorização das tarefas. Também registrei e acompanhei o andamento das Sprint Backlogs, garantindo visibilidade do progresso, alinhamento entre a equipe e aderência aos requisitos definidos.*

### Exemplo de User Storie 

| Rank | Prioridade | US | Estimativa | Sprint | Requisitos do parceiro | 
|------|------------|----|------------|--------|--------------------------|
| #01  | Alta       | Como usuário do sistema, quero fazer login com credenciais seguras, para proteger as informações dos projetos. | 15 Horas | 1 | RF5, RNF1  | 

<br>

*Além das atribuições de PO, contribuí tecnicamente no backend, desenvolvendo o CRUD, as rotas e os schemas das entidades Tarefas, Subtarefas e Áreas de Atuação, incluindo a definição de suas relações e regras de validação.*

*No frontend, atuei diretamente na integração com o backend das entidades que desenvolvi, criando funções para interpretar os JSONs retornados pela API e refatorando trechos do código React em páginas e componentes, como:*

### TaskDetails 

> *Modal responsável por exibir informações detalhadas sobre uma tarefa.*

- *Criação de useEffects para carregar subtarefas armazenadas no banco de dados.*
- *Implementação de useStates para armazenar e manipular dados das subtarefas.*
- *Definição de interfaces TypeScript para a tipagem de subtarefas.*


### Página de tarefas

> Página para visualização e gerenciamento de tarefas.

- *Criação de useEffects para carregar as tarefas existentes no banco de dados.*
- *Implementação de useStates para manipular os dados de cada tarefa.*
- *Definição de interfaces TypeScript para garantir tipagem adequada das tarefas.*



## Hard Skills
| Tecnologia     | Proficiência       | Descrição                                                                                                               |
| :------------- | :----------------- | :---------------------------------------------------------------------------------------------------------------------- |
| **React**      | faço com ajuda     | Desenvolvimento de página ecomponentes, além da integração com backend                                                  |
| **Node.js**    | faço com autonomia | Utilizado como ambiente de execução do JavaScript no servidor                                                           |
| **JavaScript** | faço com autonomia | Desenvolvimento e integração de componentes                                                                             |
| **TypeScript** | faço com autonomia | Criação de classes, tipagem estática e recursos de programação orientada a objetos                                      |
| **PostgreSQL** | faço com ajuda     | Modelagem e implementação do banco de dados, definição de regras de negócios ,criação de tabelas e relações entre elas. |
| **Git**        | faço com autonomia | Controle de versão, trabalho em equipe com branches e gestão de repositórios.                                           |


## Soft Skills

 -  **Comunicação:** *Como Product Owner, mantive contato direto com o cliente para compreender suas necessidades e garantir o alinhamento dos requisitos ao longo do desenvolvimento. Em uma das reuniões, busquei validar a regra de negócio relacionada aos filtros da aplicação, elaborando uma pergunta clara e objetiva para evitar ambiguidades e assegurar um entendimento comum entre ambas as partes. Essa abordagem facilitou a comunicação e permitiu que o cliente esclarecesse exatamente o comportamento esperado. A seguir, a mensagem enviada ao cliente para validação:*
 
##### Mensagem

>"Bom dia Walmir!
>Gostaria de saber se você está de acordo com os filtros que vamos entregar nessa sprint:• Filtro por Área de atuação
>-  Status
>- Filtro por projetos em que o usuário é coordenador
>- Filtro por projetos em que o usuário é membro

>Além disso , na questão de exclusão de um projeto, pensamos em quando o usuário deletar um projeto, enviaremos ele para uma lixeira, e em um período do de 30 dias o projeto estará disponível para recuperação, após o período ele será excluído permanentemente, você está de acordo com esta metodologia ?

>Segue também os cenários de testes que fiz com base no backlog apresentado anteriormente, relembrando que irei substituir os critérios de aceitação pelos cenários de testes."
 

- **Organização**: *Exercendo o papel de Product Owner, fui responsável pela documentação estruturada do projeto no GitHub, organizando o Product Backlog, as histórias de usuário e os Sprint Backlogs. Estruturei os artefatos do projeto em arquivos separados dentro do repositório, garantindo clareza na navegação e no versionamento. Também registrei os critérios de aceitação em formato tabular e em um arquivo dedicado. Além disso, por solicitação do cliente, foram elaborados cenários de teste para cada User Story presente no backlog. Essa organização contribuiu para uma leitura mais objetiva dos artefatos, além de facilitar o acompanhamento do progresso pela equipe ao longo das sprints.*
 
##### Exemplo de critério de aceitação 

| US      | Cenário de Teste 1                                                                                                                                                                            | Cenário de Teste 2                                                                                                                                              |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **#01** | **Ação:** Usuário acessa a página de cadastro e preenche os campos obrigatórios (nome, sobrenome, email, senha).<br>**Resultado esperado:** Sistema cria a conta e exibe mensagem de sucesso. | **Ação:** Usuário insere email e senha cadastrados na página de login.<br>**Resultado esperado:** Sistema redireciona para a dashboard e exibe boas-vindas.     |




[Voltar](../README.md)