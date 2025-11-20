#### Em 2024-2

**Empresa**: Youtan 
**Área de atuação**:  Empresa de Software
#### Problema: 
O setor de Recursos Humanos da empresa parceira enfrenta dificuldades na gestão do clima organizacional e na compreensão da satisfação dos colaboradores em relação ao ambiente de trabalho. A ausência de um processo estruturado de feedback e as falhas na comunicação interna têm dificultado o monitoramento das percepções dos funcionários, resultando em desmotivação e redução da colaboração entre as equipes.

#### Solução:
Foi desenvolvida uma aplicação web que oferece dashboards interativos para o acompanhamento das pesquisas e feedbacks organizacionais, com gráficos e indicadores que auxiliam na interpretação dos resultados.
O sistema permite a criação manual de pesquisas e o gerenciamento tabulado de equipes, usuários e pesquisas.  

<details>
A aplicação conta com dois modos de acesso:
<p>
- Modo Administrador: voltado ao setor de Recursos Humanos, permite criar equipes, cadastrar usuários, elaborar pesquisas e visualizar as respostas por meio dos dashboards.
</p>    
<p>
- Modo Usuário: destinado aos colaboradores da empresa, dividido em duas categorias — líderes e liderados.
    - Líderes têm acesso às informações e respostas de seus liderados.
    - Liderados podem visualizar apenas suas próprias informações e respostas.
 </p>       
Além disso, o modo usuário apresenta gráficos de barras que permitem acompanhar a evolução do desempenho individual ao longo do tempo.
</details>


##### [Repositório](https://github.com/Phoenix-Team-Fatec/OAK-RH)

| **Tecnologia** | **Funcionalidade**                                                                                                                               |
| :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **React**      | Biblioteca JavaScript utilizada para o desenvolvimento do frontend da aplicação, permitindo a criação de interfaces dinâmicas e componentizadas. |
| **Node.js**    | Ambiente de execução JavaScript multiplataforma, utilizado para rodar o código no servidor.                                                      |
| **JavaScript** | Linguagem de programação utilizada no desenvolvimento do projeto, responsável pela lógica de interação e integração entre os componentes.        |
| **TypeScript** | Superset do JavaScript que adiciona tipagem estática e recursos de orientação a objetos, aumentando a robustez e a manutenção do código.         |
| **PostgreSQL** | Banco de dados relacional, utilizado para armazenamento de dados do sistema                                                                      |
| **Firebase**   | Serviço em nuvem com banco de dados não relacional (NoSQL), utilizado para o armazenamento e autenticação de usuários (e-mails e senhas).        |
| **Git**        | Sistema de controle de versão distribuído, utilizado para o gerenciamento do código-fonte e colaboração em equipe.                               |
## Contribuições Pessoais
Atuando como desenvolvedor, fui responsável pela estruturação do backend seguindo o padrão de projeto MVC, organizando as pastas e arquivos de forma modular. O padrão MVC é composto por três camadas — Models, Views e Controllers — e, com base nele, a arquitetura do projeto foi definida da seguinte forma:
```bash
├── database/ 
    ├── config/ 
    ├── controllers/ 
    ├── entities/
    ├── services/ 
	├── routes.ts
├── middlewares/ 
├── server.ts
```
Realizei a conexão com o banco de dados e desenvolvi a modelagem das classes **Usuário** (administrador, líder e liderado), **Equipe**, **Perguntas** e **Formulários**, implementando um CRUD completo para cada uma delas, incluindo **models**, **services**, **controllers**, relações e rotas correspondentes. 
No frontend, contribui para o desenvolvimento da **sidebar**, integração com a biblioteca **Material UI** e comunicação com o backend por meio do **Axios**, implementando o cadastro de usuários, criação de formulários e uma tabela para controle das respostas dos participantes.


<details>
<summary>Modelagem da relação entra as classes equipe e usuário</summary>
	<pre>
		<code class="language-javascript">  
	import { Model, DataTypes } from 'sequelize';
	import sequelize from '../database/connectionDB';
	import User from './userModels';
	import Equipe from './equipeModels';
	
	class Equipe_user extends Model {
	  public id!: number;
	  public user_id!: number;
	  public equipe_id!: number;
	  public is_lider!: boolean;
	}
	
	Equipe_user.init(
	  {
	    id: {
	      type: DataTypes.INTEGER,
	      autoIncrement: true,
	      primaryKey: true,
	    },
	    user_id: {
	      type: DataTypes.INTEGER,
	      allowNull: false,
	      references: {
	        model: 'usuario', 
	        key: 'id',
	      },
	    },
	    equipe_id: {
	      type: DataTypes.INTEGER,
	      allowNull: false,
	      references: {
	        model: 'equipe', 
	        key: 'id',
	      },
	    },
	    is_lider: {
	      type: DataTypes.BOOLEAN,
	      allowNull: false,
	    },
	  },
	  {
	    sequelize,
	    modelName: 'Equipe_user',
	    tableName: 'equipe_user',
	    timestamps: false,
	  }
	);
	
	export default Equipe_user;
		</code>
	</pre>
</details>




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
- **Flexibilidade e Resiliência**: *Durante o projeto, enfrentamos uma mudança significativa no escopo, passando do desenvolvimento tradicional para a construção de uma API RESTful. Esse novo cenário exigiu rápida adaptação ao uso de métodos HTTP, criação de rotas, consumo de dados em JSON e compreensão dos princípios de arquitetura REST. Busquei me aprofundar nesses tópicos por meio de estudos adicionais e experimentação prática, o que me permitiu continuar contribuindo com o desenvolvimento sem ser impactado negativamente pelas mudanças.*

- **Proatividade**: *Tomei a iniciativa de iniciar o desenvolvimento da interface do sistema, pesquisando previamente padrões de projeto e boas práticas para aplicações modernas. Com base nisso, dei início à estruturação do frontend utilizando React e a biblioteca Material UI, definindo estilos, componentes e a organização base da aplicação. Essa ação antecipada facilitou o alinhamento visual do projeto e acelerou o avanço da equipe.*



[Voltar](../README.md)
