# microservice-design-patterns
Estudo de Microsserviços: padrões de projeto.

Neste repositório irei adicionar todas as anotações e pequenos projetos desenvolvidos para aperfeiçoamento do conteúdo em questão.

______

### Referências deste Estudo
Artigos que utilizei para compreender melhor DDD e de onde tirei todas as imagens e conclusões abaixo => 
- <a href = "https://alexalvess.medium.com/criando-uma-api-em-net-core-baseado-na-arquitetura-ddd-2c6a409c686#:~:text=O%20DDD%20(Domain%20Driven%20Design,para%20o%20dom%C3%ADnio%20do%20neg%C3%B3cio.">Começando com .NET Core, com Arquitetura em Camadas</a>
- <a href = "https://www.eduardopires.net.br/2016/08/ddd-nao-e-arquitetura-em-camadas/">DDD não é arquitetura em camadas</a>

______

### Para entender melhor

#### Como implementar o DDD
- Entender o Negócio
- Extrair a linguagem do negócio 
- Modelagem Estratégica
- Definir a Arquitetura
- Modelagem Tática

Para entendermos um pouco como funciona a arquitetura abordada nessa explicação precisamos analisar a seguinte imagem e entender um pouco o que cada módulo faz

![image](https://user-images.githubusercontent.com/50181268/224510556-6872ac8b-75d8-41ae-893e-122ad9274a0a.png)

Neste caso temos 4 módulos e cada um deles contribui da seguinte forma:

- Camada de aplicação: Onde se faz o desenvolvido dos controladores e serviços da API. Realiza o recebimento de todas as requisições e direcioa para algum serviço afim de executar uma determinada ação.(possui referências das camadas Service e Domain)
- Camada de domínio: Omde se realiza a implementação de classes/modelos, que serão mapeadas para o banco de dados, além de obter as declarações de interfaces, constantes, DTOs (Data Transfer Object) e enums. (Importante destacar que esse trecho peguei diretamente do artigo por descrever de forma muito bem redigida o que a camada de domínio faz)
- Camada de serviço: serve como cérebro do projeto, é nesta camada que se realiza todas as regras de negócio e todas as validações antes de persistir os dados no banco de dados. (Possui referências das camadas Domain, Infra.Data e Infra.CrossCutting)
- Camada de infraestrutura: é dividida em duas sub-camadas
  - Data: realiza a persistência com o banco de dados, utilizando, ou não, algum ORM.
  - Cross-Cutting: uma camada a parte que não obedece a hierarquia de camada. Como o próprio nome diz, essa camada cruza toda a hierarquia. Contém as funcionalidades que pode ser utilizada em qualquer parte do código, como, por exemplo, validação de CPF/CNPJ, consumo de API externa e utilização de alguma segurança.
Possui referências da camada Domain. (Trecho retirado do artigo)





