#### Em 2024-1

**Empresa**: _FATEC São José dos Campos - SP_
Profº Giuliano Bertoti

#### Problema: 
A empresa parceira enfrenta dificuldades relacionadas ao acesso e consulta de informações em sua base de dados corporativa. Atualmente, o processo de extração de dados é realizado de forma manual e pouco intuitiva, o que gera inconsistências nas informações utilizadas pelos colaboradores e impacta a tomada de decisão. Essas divergências comprometem a confiabilidade dos dados e resultam em retrabalho e atrasos nas atividades operacionais da equipe.

#### Solução:
Foi desenvolvida uma aplicação desktop integrada a um modelo de linguagem (LLM), que possibilita um usuário realizar consultas em suas bases de dados por meio de linguagem natural, de forma simples e intuitiva. 
O sistema permite a integração com diferentes tipos de modelos de linguagem. 

##### [Repositório](https://github.com/Phoenix-Team-Fatec/DataEase?tab=readme-ov-file)

#### Tecnologias Utilizadas
| **Tecnologia**  | **Funcionalidade**                                                                                                   |
| --------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Java **       | Linguagem responsável pelo desenvolvimento de todo o sistema, desde a interface a conexão com o modelo de linguagem. |
| **MySQL**       | Armazenamento de informações do usuário                                                                              |
| **LangChain4j** | Biblioteca do java utilizada para conexão dos modelos.                                                               |
| **LM Studio**   | Ferramenta utilizada para execução dos modelos.                                                                      |
| **Git**         | Sistema de controle de versão utilizado para gerenciar e versionar o código-fonte.                                   |

## Contribuições Pessoais
Atuando como Scrum Master, e considerando a grande complexidade técnica envolvida na solução proposta, precisei contribuir diretamente na parte técnica do projeto. Fui responsável pela integração dos modelos de linguagem à aplicação utilizando a biblioteca LangChain4j, pela modelagem das classes e pelo gerenciamento dos modelos no LM Studio. Também desenvolvi a interface da aplicação e realizei a integração dela com o código dos modelos, além de modelar e implementar todo o banco de dados.

<details>
<summary>Gerando SQL com linguagem natural</summary>
	<pre>
		<code class="language-java">  
public String getPrompt(){
	ChatLanguageModel model = LocalAiChatModel.builder()
		                .baseUrl("http://localhost:1234/v1")
		                .modelName("nsql")
		                .temperature(0.9)
		                .build();
		
		
	String languageSql = model.generate(this.getContent());
	return languageSql;
}
		</code>
	</pre>
</details>


## Hard Skills
| Tecnologia      | Proficiência       | Descrição                                                                     |
| :-------------- | :----------------- | :---------------------------------------------------------------------------- |
| **Java**        | faço com ajuda     | Desenvolvimento da interface e modelagem das classes.                         |
| **MySQL**       | faço com ajuda     | Modelagem e desenvolvimento do banco de dados                                 |
| **LangChain4j** | faço com ajuda     | Conexão com os modelos                                                        |
| **LM Studio**   | faço com ajuda     | Orquestração e execução dos modelos                                           |
| **Git**         | faço com autonomia | Controle de versão, trabalho em equipe com branches e gestão de repositórios. |


## Soft Skills
- **Liderença**: *Atuando como Scrum Master, identifiquei que parte da equipe estava com dificuldades na utilização da linguagem Java. Para compreender melhor as necessidades individuais, conversei separadamente com cada membro, buscando entender suas principais barreiras técnicas. A partir desse diagnóstico, propus a realização de cursos online gratuitos para reforçar o aprendizado e ofereci suporte direto nas tarefas de maior complexidade. Essas ações ajudaram a reduzir impedimentos e contribuíram para o avanço contínuo do time.*

- **Proatividade:** *Após a definição do design da aplicação, tomei a iniciativa de iniciar o desenvolvimento da interface utilizando Java Swing, estruturando os primeiros componentes visuais e estabelecendo o padrão de organização do frontend. Ao avançar de forma antecipada, facilitei o trabalho dos demais integrantes e acelerei a evolução inicial da aplicação.*



[Voltar](../README.md)