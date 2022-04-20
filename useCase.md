Oferecemos velocidade e confiança através de nossa Stack para times de desenvolvimento, no processo de conectar softwares de sua empresa através de uma API.  

Iniciando seu produto através de nosso template base, trazemos o benefício onde você pode buildar e executar o projeto localmente. Ressaltamos que nossa Stack não é intrusiva, criamos código para ajudar times de desenvolvimento, mas cada desenvolvedor opta pelo o que prefere usar.  

Para começar sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet aplique o template base para iniciar o desenvolvimento de uma API completa usando C#, .NET e REST, rodando em um cluster de contêiner.  

### Visão Geral
O **rest-app-cs-template** adiciona em uma stack a capacidade de provisionar serviços rest.

### Pré-requisitos
Para utilizar esse template você precisa utilizar o `CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).
- .NET 5 e/ou 6 instalados.
- Ao criar sua pipeline da AWS **e não encontrar no campo "Runtime" a opção do dotnet: 5.0**, siga as orientações descritas neste [**link**](https://confluence-itau.tecnologia.prod.ops.aws.cloud.ihf/x/GDaYJ).

### Inputs
Os inputs necessários para utilizar o template são:
| **Campo** | **Valor** | **Descrição** |
| :--- | :--- | :--- |
| Project Name| ex.: MyApp | Nome da aplicação  |
| Target Framework| 5 ou 6 | Framework em que a API será criada  |

## Execução do projeto criado

Após criar o projeto, acesse o diretório onde se encontra a `Solution` e os demais arquivos do projeto. Execute o seguinte comando:

```bash
    dotnet restore <meu App>.Api.sln
```

Realize também a compilação do projeto, através do comando abaixo:

```bash
    dotnet build <meu App>.Api.sln
```

Realize a execução dos testes unitários e de integração. Execute o seguinte comando:

```bash
dotnet test <meu App>.Api.sln
```

Para testar a aplicação, ainda no mesmo diretório da `Solution`. Execute o seguinte comando:

```bash
    dotnet run --project ./src/<meu App>.Api/<meu App>.Api.csproj
```

### Configuração do Docker

Para que o Docker funcione, você precisará adicionar um certificado SSL temporário e montar um volume para manter esse certificado.
Você pode encontrar no [Microsoft Docs](https://docs.microsoft.com/en-us/aspnet/core/security/docker-https?view=aspnetcore-6.0) que descrevem as etapas necessárias para Windows, macOS e Linux.

Para Windows:
O seguinte precisará ser executado a partir do seu terminal para criar um certificado:

```bash
dotnet dev-certs https -ep %USERPROFILE%\.aspnet\https\aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

NOTA: Ao usar o PowerShell, substitua %USERPROFILE% por $env:USERPROFILE.

PARA macOS:
```bash
dotnet dev-certs https -ep ${HOME}/.aspnet/https/aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

PARA Linux:
```bash
dotnet dev-certs https -ep ${HOME}/.aspnet/https/aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

Para construir e executar os containers docker, execute o comando abaixo na raiz da solução onde você encontra o arquivo docker-compose.yml

 ```bash
 docker-compose -f 'docker-compose.yml' up --build
 ```

Em seguida, abra http://localhost:5000 no seu navegador.

> Dica: Você também pode utilizar uma IDE (VSCode, Visual Studio) de sua preferência para realizar os passos acima.

Com a aplicação em execução, acesse a url https://localhost:5001/swagger, acesse os detalhes da aplicação e clique em "Ir para localhost (não seguro)" no Chrome. Ao acessar o endereço acima, você poderá ver a documentação (*Swagger*) da sua aplicação.

> Dica: Neste caso, a estrutura de projeto com exemplo foi criada automaticamente. 

Aplicando o projeto base pode-se adicionar capacidades ao seu template base tais como: 

#### Logging

 Se possui vários projetos, micro serviços e ou rotinas, com esse plugin você conseguirá manter a qualidade e padrão de informações de log para todas elas considerando diferentes níveis de log, permitindo definir Tags para que você consiga quantificar e/ou classificar erros trazendo uma visão de falhas recorrentes ou permitindo a prevenção de problemas futuros. Oferecemos a facilidade de integração com ferramentas como Splunk ou AWS Cloud Watch para monitorar e visualizar os dados e garantindo observabilidade de suas aplicações.

#### Metrics

Através do plugin de Metrics facilitamos a medição da quantidade de requisições em um endpoint crítico ou monitorar o tamanho de payloads que são enviados para sua API.

#### Trace

Através do plugin de Trace facilitamos a instrumentação de telemetria da sua API através do Opentelemetry com exporter para Jaeger e AWS X-Ray.

#### Queue

Imagine estar em um ambiente descentralizado voltado à micro serviços e que possua diversas comunicações entre eles através de filas de mensagens. Configurar e implementar o manuseio dessas filas será mais simples com o queue plugin. Assim como criar uma classe, abstraindo toda a complexidade para comunicação com sua fila AWS SQS.

#### Secrets

Lidar com informações sensíveis de sistemas com chaves de APIs, tokens de autenticação ou conexões com bases de dados, tendo em vista a utilização de um Secret Manager como o da AWS ficará mais fácil e seguro com o secrets plugin onde ele simplifica o consumo dessas informações e você poderá utilizar no momento que desejar dentro de sua aplicação.  

#### Bucket

Manipule arquivos utilizando este plugin que facilita a instrumentação com a Amazon Simple Storage Service (S3), eliminando a complexidade.

#### Repository

Armazenar dados ou documentos de forma trivial é um desafio para quase todos os sistemas, e com esse plugin você tem todas as capacidades do AWS DynamoDB disponíveis de forma simples e rápida.

#### Authentication

Através deste plugin facilitamos a capacidade de verificar se um usuário/API possui acesso a um determinado recurso restrito trazendo segurança para sua API.

#### ErrorHandler

Manipule, padronize e personalize os retornos de erro em sua api REST.

#### gRPC

Através deste plugin é possível adicionar capacidade de expor serviços `gRPC` e suas configurações, bem como prover a criação de um `gRPC Client` que permite a distribuição e consumo desse serviço em outras aplicações.

Ao fim do ciclo de desenvolvimento utilizando todas as capacidades que nossa Stack oferece podemos ter uma estrutura completa como ilustra imagem abaixo:

![Caso de Uso](https://raw.githubusercontent.com/stack-spot/skynet-dotnet-stack/main/use-case.png "Caso de Uso")

Veja mais detalhes de cada plugin disponível através do menu lateral esquerdo onde vocês podem ver detalhes mais aprofundados de cada um, casos de uso e formas de uso. 
