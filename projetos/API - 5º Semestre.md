#### Em 2025-2

**Empresa**: Visiona
<br>
**Área de atuação**: Geoespacial
#### Problema: 
A população residente em áreas rurais enfrenta dificuldades relacionadas à ausência de endereços formais. Essa limitação compromete a identificação e a localização dessas residências por órgãos governamentais, além de dificultar a realização de entregas de produtos e o acesso de familiares e visitantes. A falta de um sistema padronizado de endereçamento impacta diretamente a integração dessas comunidades a serviços essenciais, afetando sua inclusão social e logística.
#### Solução:
Foi desenvolvida uma aplicação mobile que permite o cadastro de usuários por meio de informações pessoais, como nome, CPF, e-mail, data de nascimento e fotografia. A partir do CPF informado, o sistema realiza a identificação do código CAR do imóvel associado ao usuário.
Após o cadastro e autenticação, a aplicação disponibiliza um mapa interativo que permite a visualização da propriedade por meio de uma área demarcada. Caso o imóvel não possua endereço formal, o sistema possibilita a geração de um endereço digital (Plus Code) a partir do centróide da propriedade ou da seleção de um ponto dentro de seus limites, além de permitir a atualização do endereço e a consulta ao histórico de alterações.
A solução também oferece funcionalidades de rotas e alertas, possibilitando ao usuário definir trajetos e visualizar condições climáticas e alertas ao longo do percurso. Usuários cadastrados podem registrar alertas viários, classificados por grau de gravidade (leve, moderado ou grave) e por tipo, como trânsito, acidente, veículo no acostamento ou presença da polícia rodoviária.
Por fim, foi desenvolvida uma aplicação web para o gerenciamento da solução mobile, permitindo o controle de usuários registrados e dos alertas cadastrados no sistema


##### [Repositório](https://github.com/Phoenix-Team-Fatec/geo-maps)

| **Tecnologia** | **Funcionalidade**                                                                                                                               |
| :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **React Native**      |Biblioteca JavaScript utilizada no desenvolvimento do frontend da aplicação móvel, permitindo a criação de interfaces dinâmicas e componentizadas. |
| **Python**   | Linguagem de programação utilizada no desenvolvimento do backend e na implementação das regras de negócio do sistema.  |
| **Node.js**    |Ambiente de execução JavaScript multiplataforma, utilizado para executar o código do servidor e suportar a aplicação web.                                            |
| **MongoDB** |Banco de dados não relacional (NoSQL), utilizado para o armazenamento de dados relacionados a usuários, imóveis e alertas.        |
| **FastAPI**     | Framework utilizado para a criação da API RESTful, responsável pela comunicação entre frontend e backend.                                                                     |
| **Docker**     |Ferramenta utilizada para a conteinerização e o deploy da aplicação, garantindo padronização do ambiente de execução.                                                                  |
| **JavaScript** | Linguagem de programação utilizada no desenvolvimento da aplicação web (painel administrativo), responsável pela lógica de interação e integração entre componentes.     |
| **TypeScript** | Superset do JavaScript que adiciona tipagem estática e recursos de orientação a objetos, aumentando a robustez e a manutenção do código.         |
| **Git**        | Sistema de controle de versão distribuído, utilizado para o gerenciamento do código-fonte e colaboração em equipe.                               |
## Contribuições Pessoais
*Atuando como Desenvolvedor, fui responsável pela criação e configuração dos submódulos Git, separando o projeto em dois repositórios distintos, um destinado ao frontend e outro ao backend. Em seguida, realizei a configuração inicial da API, instalando as bibliotecas necessárias ao desenvolvimento e registrando-as no arquivo `requirements.txt`. Também estruturei as pastas do projeto seguindo um padrão de arquitetura em camadas, adotando boas práticas de desenvolvimento, como os princípios de Clean Code.*
<br>

*Desenvolvi o código base para o funcionamento do FastAPI, incluindo a criação do arquivo `main.py` para inicialização do servidor e a configuração da conexão com o banco de dados. Para isso, utilizei o driver oficial do MongoDB para Python (PyMongo). Além disso, fui responsável pela implementação da funcionalidade de geração e atualização do Plus Code (endereço digital) associado a uma propriedade, utilizando a biblioteca geoespacial Shapely. Também desenvolvi a rota HTTP responsável pela comunicação dessa funcionalidade com o frontend.*.
<br>

*Com base nos dados fornecidos pela empresa parceira, criei um Jupyter Notebook no Google Colab para realizar a exploração inicial dos dados, analisando o tamanho da base e identificando possíveis duplicidades por meio da biblioteca Pandas. Após essa etapa, realizei a conversão dos arquivos para o formato JSON, viabilizando a construção da base de dados no MongoDB.*
<br>

*Também desenvolvi scripts para manipulação e padronização dos dados, criando schemas para a estrutura dos arquivos JSON. Além disso, implementei funções e rotas responsáveis pela seleção de propriedades com base no CPF do usuário ou no Plus Code associado ao imóvel.*
<br>

*Por fim, fui responsável pela documentação completa do backend, detalhando a estrutura do projeto, o fluxo do código e as instruções necessárias para execução da aplicação em ambiente local, permitindo que outros desenvolvedores possam clonar e utilizar o repositório corretamente.*

### Estrutura da api
```bash
├── app/ 
    ├── core/ 
    ├── main.py 
    ├── models/
    ├── repositories/ 
    ├── routes/ 
    ├── schemas/ 
    ├── services/ 
    ├── utils/ 
    ├── main.py
├── requirements.txt 
```

### Conexão com o banco de dados 
```python
from pymongo import AsyncMongoClient
import os
from dotenv import load_dotenv

load_dotenv()

MONGO_URL = os.environ.get('MONGO_URL')
DB_NAME = os.environ.get('DB_NAME')

client = AsyncMongoClient(MONGO_URL)

db = client[DB_NAME]

collection = db['area_imovel_projeto']
users_collection = db["users"]

async def ensure_indexes():
    await users_collection.create_index(
        "email",
        name="uniq_email",
        unique=True,
        partialFilterExpression={"email": {"$exists": True, "$type": "string"}}
    )
    await users_collection.create_index(
        "cpf",
        name="uniq_cpf",
        unique=True,
        partialFilterExpression={"cpf": {"$exists": True, "$type": "string"}}
    )

if __name__ == "__main__":
    print("Conexão com o Mongo feita com sucesso")
```

### Função e rota do pluscode
```python
def generate_plus_code(lat: float, long: float) -> str:
    try:
        propertie_pluscode = pluscodes.encode(lat, long)
        return propertie_pluscode
    except Exception as e:
        raise Exception(f"Erro ao gerar o pluscode: {e}")


@area_imovel_router.post('/properties/{cod_imovel}/pluscode')
async def add_pluscode(cod_imovel: str, request: CreatePlusCode):
    try:
        property_pluscode = await add_properties_plus_code_service(cod_imovel, request)
        return {
            "message": "PlusCode adicionado com sucesso",
            "cod_imovel": cod_imovel,
            "result": property_pluscode
        }
    except Exception as e:
        raise HTTPException(status_code=400, detail=str(e))
```


<br>

*Por fim, desenvolvi o portal do administrador, utilizando React para a criação das páginas de login, gerenciamento de usuários e administração de ocorrências, garantindo a integração com o backend desenvolvido.*


## Hard Skills
| Tecnologia     | Proficiência       | Descrição                                                                                                               |
| :------------- | :----------------- | :---------------------------------------------------------------------------------------------------------------------- |
| **React**      | faço com ajuda     | Desenvolvimento de página ecomponentes, além da integração com backend                                                  |
| **Python**     | faço com autonomia | Desenvolvimento da api RESTFul e scripts para comunicação com o banco de dados                                                                                          |
| **Node.js**    | faço com autonomia | Utilizado como ambiente de execução do JavaScript no servidor                                                           |
| **JavaScript** | faço com autonomia | Desenvolvimento e integração de componentes                                                                             |
| **TypeScript** | faço com autonomia | Criação de classes, tipagem estática e recursos de programação orientada a objetos                                      |
| **MongoDB** | faço com ajuda     | Modelagem e implementação do banco de dados não relacional, definição de regras de negócios ,criação de collections, documents e relações entre eles |
| **Git**        | faço com autonomia | Controle de versão, trabalho em equipe com branches e gestão de repositórios.                                           |


## Soft Skills

 -  **Comunicação:** *Durante o planejamento do projeto, identifiquei limitações técnicas do Django em relação à integração com o banco de dados não relacional MongoDB, o que poderia comprometer o andamento do desenvolvimento. Diante dessa situação, preparei uma argumentação técnica e a apresentei à equipe durante uma das reuniões, propondo a migração do framework para o FastAPI. Busquei expor os pontos de forma clara e objetiva, destacando os benefícios em termos de organização, escalabilidade e compatibilidade com o banco de dados, de modo a facilitar a compreensão de todos os membros e promover uma tomada de decisão coletiva e fundamentada.*


- **Proatividade**: *Diante da demanda de criação de um portal administrativo para a aplicação, tomei a iniciativa de antecipar o desenvolvimento do frontend antes mesmo da definição formal das tarefas pela equipe. Realizei pesquisas sobre estruturas adequadas para painéis administrativos e, com base nisso, dei início à construção da interface utilizando React, definindo a organização dos componentes, as rotas e a estrutura base do projeto. Essa ação antecipada permitiu que a equipe tivesse um ponto de partida consolidado, agilizando as entregas subsequentes da sprint.*
 

[Voltar](../README.md)